## <ws-api Demo (java)

```java

package test;

import java.io.ByteArrayInputStream;
import java.io.ByteArrayOutputStream;
import java.io.IOException;
import java.net.URI;
import java.nio.ByteBuffer;
import java.nio.CharBuffer;
import java.nio.charset.Charset;
import java.nio.charset.CharsetDecoder;
import java.security.cert.CertificateException;
import java.security.cert.X509Certificate;
import java.util.HashMap;
import java.util.Map;
import java.util.zip.GZIPInputStream;

import javax.net.ssl.SSLContext;
import javax.net.ssl.TrustManager;
import javax.net.ssl.X509TrustManager;

import org.java_websocket.client.DefaultSSLWebSocketClientFactory;
import org.java_websocket.client.WebSocketClient;
import org.java_websocket.drafts.Draft;
import org.java_websocket.drafts.Draft_17;
import org.java_websocket.handshake.ServerHandshake;

/**
 * @author Squid DateTime:November 22, 2018, 9:25:20 PM 
 * Suggested use websocket client Edition 
 * <dependency> 
 * <groupId>org.java-websocket</groupId> 
 * <artifactId>Java-WebSocket</artifactId> 
 * <version>1.3.0</version> 
 * </dependency> 
 *
 */
public class WsTest {

    public static void main(String[] args) {
        try {
//wsurl 
            String url = "wss://ws.Exchange.com/kline-api/ws";
//Historical data request parameters 
            String reqParam = "{"event":"req","params":{"channel":"market_btcusdt_trade_ticker","cb_id":"btcusdt","top":150}}";
//Subscription parameters 
            String subParam = "{"event":"sub","params":{"channel":"market_btcusdt_trade_ticker","cb_id":"btcusdt","top":150}}";

//Initialization request history data 
            WebSocketUtils wsc = WebSocketUtils.executeWebSocket(url, reqParam);

//Subscribe to real-time data 
            wsc.send(subParam);

//Thread does not end, waiting for new messages，www.Exchange.com Generally, a new deal will return in about a minute
            while (true) {
                Thread.sleep(1000);
            }

        }catch (Exception e) {
            e.printStackTrace();
        }
    }

    static class WebSocketUtils extends WebSocketClient {
        private static WebSocketUtils wsclient = null;
        private String msg = "";

        public WebSocketUtils(URI serverURI) {
            super(serverURI);
        }

        public WebSocketUtils(URI serverUri, Draft draft) {
            super(serverUri, draft);
        }

        public WebSocketUtils(URI serverUri, Map<String, String> headers, int connecttimeout) {
            super(serverUri, new Draft_17(), headers, connecttimeout);
        }

        @Override
        public void onOpen(ServerHandshake serverHandshake) {
            System.out.println("Links have been established");

        }

        @Override
        public void onMessage(String s) {
            System.out.println("Receive a string message");
        }

        @Override
        public void onClose(int i, String s, boolean b) {
            System.out.println("Link closed");
        }

        @Override
        public void onError(Exception e) {
            System.out.println("Wrong report");
        }

        @Override
        public void onMessage(ByteBuffer socketBuffer) {
            try {
                String marketStr = byteBufferToString(socketBuffer);
                String market = uncompress(marketStr).toLowerCase();
                if (market.contains("ping")) {
                    System.out.println("Receive messageping："+market);
                    String tmp = market.replace("ping", "pong");
                    wsclient.send(market.replace("ping", "pong"));
                } else {
                    msg = market;
                    System.out.println("Receive message："+msg);
                }
            } catch (IOException e) {
                e.printStackTrace();
            }
        }

        public static Map<String, String> getWebSocketHeaders() throws IOException {
            Map<String, String> headers = new HashMap<String, String>();
            return headers;
        }

        private static void trustAllHosts(WebSocketUtils appClient) {
            TrustManager[] trustAllCerts = new TrustManager[] { new X509TrustManager() {
                public java.security.cert.X509Certificate[] getAcceptedIssuers() {
                    return new java.security.cert.X509Certificate[] {};
                }

                public void checkClientTrusted(X509Certificate[] chain, String authType) throws CertificateException {
                }

                public void checkServerTrusted(X509Certificate[] chain, String authType) throws CertificateException {
                }
            } };

            try {
                SSLContext sc = SSLContext.getInstance("TLS");
                sc.init(null, trustAllCerts, new java.security.SecureRandom());
                appClient.setWebSocketFactory(new DefaultSSLWebSocketClientFactory(sc));
            } catch (Exception e) {
                e.printStackTrace();
            }
        }

        public static WebSocketUtils executeWebSocket(String url,String sendMsg) throws Exception {
            wsclient = new WebSocketUtils(new URI(url), getWebSocketHeaders(), 1000);
            trustAllHosts(wsclient);
            wsclient.connectBlocking();
            wsclient.send(sendMsg);
            return wsclient;
        }

        // buffer turn String 
        public String byteBufferToString(ByteBuffer buffer) {
            CharBuffer charBuffer = null;
            try {
                Charset charset = Charset.forName("ISO-8859-1");
                CharsetDecoder decoder = charset.newDecoder();
                charBuffer = decoder.decode(buffer);
                buffer.flip();
                return charBuffer.toString();
            } catch (Exception ex) {
                ex.printStackTrace();
                return null;
            }
        }

        // decompression 
        public String uncompress(String str) throws IOException {
            if (str == null || str.length() == 0) {
                return str;
            }
            ByteArrayOutputStream out = new ByteArrayOutputStream();
            ByteArrayInputStream in = new ByteArrayInputStream(str.getBytes("ISO-8859-1"));
            GZIPInputStream gunzip = new GZIPInputStream(in);
            byte[] buffer = new byte[256];
            int n;
            while ((n = gunzip.read(buffer)) >= 0) {
                out.write(buffer, 0, n);
            }
            return out.toString();
        }

    }
}

```
