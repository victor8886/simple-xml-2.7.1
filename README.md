# simple-xml-2.7.1
xml解析工具类，使用时可作为moudle导入Android studio
简单用法：
1.使用simplexml-format插件生成对应的bean
2.创建解析器 Serializer serializer = new Persister();
3.调用serializer.read()方法解析数据


单元测试如下：
import org.junit.Test;
import org.simpleframework.xml.Serializer;
import org.simpleframework.xml.core.Persister;

import static org.junit.Assert.*;

/**
 * Example local unit test, which will execute on the development machine (host).
 *
 * @see <a href="http://d.android.com/tools/testing">Testing documentation</a>
 */
public class ExampleUnitTest {
    @Test
    public void addition_isCorrect() throws Exception {
        assertEquals(4, 2 + 2);
    }

    @Test
    public void parseTest()throws Exception {
        //模拟测试数据
        String response = "<?xml version=\"1.0\" encoding=\"utf-8\"?>\n" +
                "\n" +
                "<EPOSPROTOCOL>\n" +
                "  <RSPCOD>00</RSPCOD>\n" +
                "  <RSPMSG>交易成功</RSPMSG>\n" +
                "  <POPULARIZE_STATUS_INFO>推广成功:6/13</POPULARIZE_STATUS_INFO>\n" +
                "  <TOTAL>13</TOTAL>\n" +"" +
                "   <ASD>565</ASD>\n"+
                "  <BIND_TERMINAL_TOTAL>5</BIND_TERMINAL_TOTAL>\n" +
                "  <SHOP_UPGRADE_TOTAL>6</SHOP_UPGRADE_TOTAL>\n" +
                "  <TRANDETAILS>\n" +
                "    <TRANDETAIL>\n" +
                "      <SON_SHOP_PHONE_NO>18100000012</SON_SHOP_PHONE_NO>\n" +
                "      <IMAGE_URL></IMAGE_URL>\n" +
                "      <TERMINAL_STATUS>0</TERMINAL_STATUS>\n" +
                "      <SON_SHOP_UPGRADE_FLAG>1</SON_SHOP_UPGRADE_FLAG>\n" +
                "      <INVITE_TIME>2017-09-15 00:56:04</INVITE_TIME>\n" +
                "    </TRANDETAIL>\n" +
                "    <TRANDETAIL>\n" +
                "      <SON_SHOP_PHONE_NO>18100000011</SON_SHOP_PHONE_NO>\n" +
                "      <IMAGE_URL/>\n" +
                "      <TERMINAL_STATUS>0</TERMINAL_STATUS>\n" +
                "      <SON_SHOP_UPGRADE_FLAG>0</SON_SHOP_UPGRADE_FLAG>\n" +
                "      <INVITE_TIME>2017-09-15 00:39:06</INVITE_TIME>\n" +
                "    </TRANDETAIL>\n" +
                "    <TRANDETAIL>\n" +
                "      <SON_SHOP_PHONE_NO>15201704952</SON_SHOP_PHONE_NO>\n" +
                "      <IMAGE_URL/>\n" +
                "      <TERMINAL_STATUS>0</TERMINAL_STATUS>\n" +
                "      <SON_SHOP_UPGRADE_FLAG>0</SON_SHOP_UPGRADE_FLAG>\n" +
                "      <INVITE_TIME>2017-08-28 17:20:45</INVITE_TIME>\n" +
                "    </TRANDETAIL>\n" +
                "    <TRANDETAIL>\n" +
                "      <SON_SHOP_PHONE_NO>18100000009</SON_SHOP_PHONE_NO>\n" +
                "      <IMAGE_URL/>\n" +
                "      <TERMINAL_STATUS>0</TERMINAL_STATUS>\n" +
                "      <SON_SHOP_UPGRADE_FLAG>0</SON_SHOP_UPGRADE_FLAG>\n" +
                "      <INVITE_TIME>2017-08-21 12:35:02</INVITE_TIME>\n" +
                "    </TRANDETAIL>\n" +
                "    <TRANDETAIL>\n" +
                "      <SON_SHOP_PHONE_NO>18100000005</SON_SHOP_PHONE_NO>\n" +
                "      <IMAGE_URL/>\n" +
                "      <TERMINAL_STATUS>1</TERMINAL_STATUS>\n" +
                "      <SON_SHOP_UPGRADE_FLAG>1</SON_SHOP_UPGRADE_FLAG>\n" +
                "      <INVITE_TIME>2017-08-18 11:29:38</INVITE_TIME>\n" +
                "    </TRANDETAIL>\n" +
                "    <TRANDETAIL>\n" +
                "      <SON_SHOP_PHONE_NO>13651869115</SON_SHOP_PHONE_NO>\n" +
                "      <IMAGE_URL/>\n" +
                "      <TERMINAL_STATUS>0</TERMINAL_STATUS>\n" +
                "      <SON_SHOP_UPGRADE_FLAG>0</SON_SHOP_UPGRADE_FLAG>\n" +
                "      <INVITE_TIME>2017-08-12 09:12:13</INVITE_TIME>\n" +
                "    </TRANDETAIL>\n" +
                "    <TRANDETAIL>\n" +
                "      <SON_SHOP_PHONE_NO>18616264795</SON_SHOP_PHONE_NO>\n" +
                "      <IMAGE_URL/>\n" +
                "      <TERMINAL_STATUS>1</TERMINAL_STATUS>\n" +
                "      <SON_SHOP_UPGRADE_FLAG>1</SON_SHOP_UPGRADE_FLAG>\n" +
                "      <INVITE_TIME>2017-08-12 09:12:12</INVITE_TIME>\n" +
                "    </TRANDETAIL>\n" +
                "    <TRANDETAIL>\n" +
                "      <SON_SHOP_PHONE_NO>15255889398</SON_SHOP_PHONE_NO>\n" +
                "      <IMAGE_URL></IMAGE_URL>\n" +
                "      <TERMINAL_STATUS>0</TERMINAL_STATUS>\n" +
                "      <SON_SHOP_UPGRADE_FLAG>1</SON_SHOP_UPGRADE_FLAG>\n" +
                "      <INVITE_TIME>2017-08-12 08:59:16</INVITE_TIME>\n" +
                "    </TRANDETAIL>\n" +
                "    <TRANDETAIL>\n" +
                "      <SON_SHOP_PHONE_NO>13761313551</SON_SHOP_PHONE_NO>\n" +
                "      <IMAGE_URL>customerHead/20170814/2017081413571841339.png</IMAGE_URL> \n" +
                "      <TERMINAL_STATUS>1</TERMINAL_STATUS>\n" +
                "      <SON_SHOP_UPGRADE_FLAG>0</SON_SHOP_UPGRADE_FLAG>\n" +
                "      <INVITE_TIME>2017-08-12 08:20:43</INVITE_TIME>\n" +
                "    </TRANDETAIL>\n" +
                "    <TRANDETAIL>\n" +
                "      <SON_SHOP_PHONE_NO>18000000466</SON_SHOP_PHONE_NO>\n" +
                "      <IMAGE_URL></IMAGE_URL>\n" +
                "      <TERMINAL_STATUS>0</TERMINAL_STATUS>\n" +
                "      <SON_SHOP_UPGRADE_FLAG>1</SON_SHOP_UPGRADE_FLAG>\n" +
                "      <INVITE_TIME>2017-08-12 07:28:12</INVITE_TIME>\n" +
                "    </TRANDETAIL>\n" +
                "    <TRANDETAIL>\n" +
                "      <SON_SHOP_PHONE_NO>15800309635</SON_SHOP_PHONE_NO>\n" +
                "      <IMAGE_URL>customerHead/20170812/20170812070739841714.png</IMAGE_URL> \n" +
                "       <TEST>test</TEST>"+
                "      <TERMINAL_STATUS>1</TERMINAL_STATUS>\n" +
                "      <SON_SHOP_UPGRADE_FLAG>1</SON_SHOP_UPGRADE_FLAG>\n" +
                "      <INVITE_TIME>2017-08-12 07:05:44</INVITE_TIME>\n" +
                "    </TRANDETAIL>\n" +
                "    <TRANDETAIL>\n" +
                "      <SON_SHOP_PHONE_NO>18100000002</SON_SHOP_PHONE_NO>\n" +
                "      <IMAGE_URL/>\n" +
                "      <TERMINAL_STATUS>0</TERMINAL_STATUS>\n" +
                "      <SON_SHOP_UPGRADE_FLAG>0</SON_SHOP_UPGRADE_FLAG>\n" +
                "      <INVITE_TIME>2017-08-12 06:35:02</INVITE_TIME>\n" +
                "    </TRANDETAIL>\n" +
                "    <TRANDETAIL>\n" +
                "      <SON_SHOP_PHONE_NO>18100000001</SON_SHOP_PHONE_NO>\n" +
                "      <IMAGE_URL/>\n" +
                "      <TERMINAL_STATUS>1</TERMINAL_STATUS>\n" +
                "      <SON_SHOP_UPGRADE_FLAG>0</SON_SHOP_UPGRADE_FLAG>\n" +
                "      <INVITE_TIME>2017-08-12 06:32:58</INVITE_TIME>\n" +
                "    </TRANDETAIL>\n" +
                "  </TRANDETAILS>\n" +
                "</EPOSPROTOCOL>";
        //创建解析器
        Serializer serializer = new Persister();
        //bean对象
        MerchantListResponse list;
        //开始解析数据
        list = serializer.read(MerchantListResponse.class, response);
    }
}

详细用法参见官方文档：http://simple.sourceforge.net/download/stream/doc/tutorial/tutorial.php
