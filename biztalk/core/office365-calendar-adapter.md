---
title: 使用 Office 365 Outlook 日历适配器 |Microsoft Docs
description: 发送和接收消息在 BizTalk Server 中使用 Office 365 Outlook 日历适配器。 使用适配器创建和使用接收端口的日历事件接收和发送端口，并使用示例 XML 消息创建日历事件。
ms.custom: ''
ms.date: 06/25/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
author: MandiOhlinger
ms.author: ribarua
manager: dougeby
ms.openlocfilehash: ab724870e9c75a60119e86f7f62d6823f1db9873
ms.sourcegitcommit: e7609c319b64ec20bf215d17aa5ac4f9dcae52ec
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2018
ms.locfileid: "36946154"
---
# <a name="create-calendar-events-with-the-office-365-outlook-calendar-adapter---biztalk-server"></a>使用 Office 365 Outlook 日历适配器的 BizTalk Server 创建日历事件

在 BizTalk Server 中使用 Office 365 Outlook 日历适配器创建并接收来自 Office 365 Outlook 日历的日历事件。

## <a name="create-events-using-a-send-port"></a>创建事件使用的发送端口

1. 在 BizTalk Server 管理控制台中，右键单击**发送端口**，选择**新建**，然后选择**静态单向发送端口**。

    [创建发送端口](../core/how-to-create-a-send-port2.md)提供一些指导。

2. 输入**名称**。 在**传输**，请设置**类型**到**Office 365 Outlook 日历**，然后选择**配置**。

3. 选择 **[登录...**，并登录到你的 Office 365 帐户。 该帐户是使用你的电子邮件地址自动填充。

4. 允许 BizTalk Server 的访问权限的审批请求：

    ![Office 365 日历权限](../core/media/office365-calendar-permissions.png)

5. 配置您 Office365 Outlook 日历的默认属性：

    |使用此选项|执行的操作|  
    |---|---|  
    | **日历** | 选择要在其中创建事件的日历。 |
    | **主题** | 设置创建的事件的默认主题。 （最多 256 个字符） |
    | **必需的与会者** | 输入所需的默认与会者电子邮件地址分隔;。 （最多 256 个字符） |
    | **可选与会者** | 输入可选与会者电子邮件地址分隔应用默认值;。 （最多 256 个字符） |

6. 选择日历： 

    ![Office 365 日历](../core/media/office365-calendars.png)

    完成后，您的属性类似于以下：

    ![终结点属性](../core/media/office365-calendar-send-properties.png)

7. 选择**确定**以保存所做的更改。

### <a name="test-your-send-port"></a>测试您的发送端口

可以使用简单文件接收端口和位置来创建 Office 365 Outlook 日历上的事件。

1. 创建使用文件适配器的接收端口。 在你接收位置，则设置**接收文件夹**到 **C:\Temp\In\**，并将文件掩码设置为 **\*.xml**。
2. 在您的 Office 365 Outlook 日历适配器发送端口属性，设置**筛选器**到`BTS.ReceivePortName == <Receive Port Name>`。
3. 将以下粘贴到文本编辑器中，并将该文件作为**Office365Calendar.xml**。 这是您的示例消息。

    ```xml
    <Event xmlns="http://schemas.microsoft.com/BizTalk/Office365OutlookCalendar/Send"> 
        <subject>Test event 1</subject> 
        <body> 
        <contentType>html</contentType> 
        <content>&lt;html&gt; 
        &lt;head&gt; 
        &lt;meta http-equiv="Content-Type" content="text/html; charset=utf-8"&gt; 
        &lt;meta content="text/html; charset=us-ascii"&gt; 
        &lt;/head&gt; 
        &lt;body&gt; 
        Test body for event Test event 1 
        &lt;/body&gt; 
        &lt;/html&gt; 
        </content> 
        </body> 
    </Event> 
    ```
    **在 < BizTalk 安装 Folder\SDK\Schemas > SDK 的一部分提供的 XML 架构**

4. 启动文件接收位置和 Office 365 Outlook 日历适配器发送端口。
5. 复制**Office365Calendar.xml**到接收文件夹的示例消息 (C:\Temp\In\)。 发送端口基于 xml 在 Office 365 Outlook 日历中创建的事件。

## <a name="receive-events-using-a-receive-port"></a>使用接收端口接收事件

1. 在 BizTalk Server 管理控制台中，右键单击**接收端口**，选择**新建**，然后选择**单向接收端口**。

    [创建接收端口](../core/how-to-create-a-receive-port.md)提供一些指导。

2. 输入一个名称，并选择**接收位置**。

3. 选择**新建**，并**名称**接收位置。 在中**传输**，选择**Office 365 Outlook 日历**从**类型**下拉列表，然后选择**配置**。

4. 选择**登录...**，并登录到你的 Office 365 帐户。 该帐户是使用你的电子邮件地址自动填充。

5. 允许 BizTalk Server 的访问权限的审批请求：

    ![Office 365 日历权限](../core/media/office365-calendar-permissions.png)

6. 配置**终结点**属性：

    |使用此选项|执行的操作|  
    |---|---|  
    | **日历** | 选择要从其提取事件的日历。  |
    | **内开始** | 选择日历事件必须在其中以接收的 BizTalk （默认值为 15 分钟） 的开始的时间间隔。  |

7. 选择一个日历：

    ![Office 365 日历](../core/media/office365-calendars.png)

    完成后，您的属性类似于以下：

    ![终结点属性](../core/media/office365-calendar-receive-properties.png)

8. 选择**确定**以保存所做的更改。

### <a name="test-your-receive-settings"></a>测试在接收设置

可以使用简单的 File 发送端口从 Office 365 Outlook 日历接收消息。

1. 创建使用文件适配器的发送端口。 在发送端口的属性，设置**目标文件夹**到 **C:\Temp\Out\**，并将设置和**文件的名称**到 **%MessageID%.xml**.
2. 在你的文件将发送端口属性，设置**筛选器**到`BTS.ReceivePortName == <Receive Port Name>`。
3. 启动 Office 365 Outlook 日历接收位置和 File 发送端口。
4. 查找目标文件夹 (c:\temp\out) 中的消息。 
**在 SDK 中包含的 XML 架构`\Program Files (x86)\Microsoft BizTalk Server <your version>\SDK\Schemas`。**

### <a name="example-of-a-received-calendar-event-xml"></a>已接收的日历事件 xml 的示例

```xml
<ns0:Event xmlns:ns0="http://schemas.microsoft.com/BizTalk/Office365OutlookCalendar/Receive"> 
<reminderMinutesBeforeStart>20160</reminderMinutesBeforeStart> 
<importance>normal</importance> 
<subject>Let's meet</subject> 
<id>AQMkADAwATNiZmYAZC0xMQBlOC0yODQ1LTA</id> 
<body> 
<contentType>html</contentType> 
<content>&lt;html&gt; 
&lt;head&gt; 
&lt;meta http-equiv="Content-Type" content="text/html; charset=utf-8"&gt; 
&lt;meta content="text/html; charset=us-ascii"&gt; 
&lt;meta name="ProgId" content="Word.Document"&gt; 
&lt;meta name="Generator" content="Microsoft Word 15"&gt; 
&lt;meta name="Originator" content="Microsoft Word 15"&gt; 
&lt;link rel="File-List" href="cid:filelist.xml@01D40724.27036CE0"&gt;&lt;style&gt; 
&lt;!-- 
@font-face 
  {font-family:"Cambria Math"} 
@font-face 
  {font-family:Calibri} 
p.MsoNormal, li.MsoNormal, div.MsoNormal 
  {margin:0in; 
  margin-bottom:.0001pt; 
  font-size:11.0pt; 
  font-family:"Calibri",sans-serif} 
a:link, span.MsoHyperlink 
  {color:#0563C1; 
  text-decoration:underline} 
a:visited, span.MsoHyperlinkFollowed 
  {color:#954F72; 
  text-decoration:underline} 
span.EmailStyle17 
  {font-family:"Calibri",sans-serif; 
  color:windowtext} 
.MsoChpDefault 
  {font-family:"Calibri",sans-serif} 
@page WordSection1 
  {margin:1.0in 1.0in 1.0in 1.0in} 
div.WordSection1 
  {} 
--&gt; 
&lt;/style&gt; 
&lt;/head&gt; 
&lt;body lang="EN-US" link="#0563C1" vlink="#954F72" style=""&gt; 
&lt;div class="WordSection1"&gt; 
&lt;p class="MsoNormal"&gt;Let’s sync up.&lt;/p&gt; 
&lt;/div&gt; 
&lt;/body&gt; 
&lt;/html&gt; 
</content> 
</body> 
<bodyPreview>Let’s sync up.</bodyPreview> 
<attendees> 
<type>required</type> 
<status> 
<response>none</response> 
<time>0001-01-01T00:00:00Z</time> 
</status> 
<emailAddress> 
<name>someone@contoso.com</name> 
<address>someone@contoso.com</address> 
</emailAddress> 
</attendees> 
<start> 
<dateTime>2018-06-25T17:00:00</dateTime> 
<timeZone>UTC</timeZone> 
</start> 
<end> 
<dateTime>2018-06-25T17:30:00</dateTime> 
<timeZone>UTC</timeZone> 
</end> 
<location> 
<displayName>Your office</displayName> 
<locationType>default</locationType> 
<uniqueId>Your office</uniqueId> 
<uniqueIdType>private</uniqueIdType> 
</location> 
<responseRequested>true</responseRequested> 
<seriesMasterId /> 
<isCancelled>false</isCancelled> 
<isOrganizer>true</isOrganizer> 
<createdDateTime>2018-06-18T23:48:35.0164728Z</createdDateTime> 
<lastModifiedDateTime>2018-06-18T23:48:22.178Z</lastModifiedDateTime> 
<hasAttachments>false</hasAttachments> 
<responseStatus> 
<response>none</response> 
<time>0001-01-01T00:00:00Z</time> 
</responseStatus> 
<changeKey>SFa3sLJfdiDEIpfwAAIAU=</changeKey> 
<originalStartTimeZone>Pacific Standard Time</originalStartTimeZone> 
<originalEndTimeZone>Pacific Standard Time</originalEndTimeZone> 
<isReminderOn>false</isReminderOn> 
<sensitivity>normal</sensitivity> 
<isAllDay>false</isAllDay> 
<showAs>busy</showAs> 
<type>singleInstance</type> 
<onlineMeetingUrl /> 
<recurrence /> 
<locations> 
<displayName>Your office</displayName> 
<locationType>default</locationType> 
<uniqueId>Your office</uniqueId> 
<uniqueIdType>private</uniqueIdType> 
</locations> 
<organizer> 
<emailAddress> 
<name>someone@contoso.com</name> 
<address>/O=FIRST ORGANIZATION/OU=EXCHANGE ADMINISTRATIVE GROUP(FYDIBOH3SPDLT)/CN=RECIPIENTS/CN=0003B11E8245</address> 
</emailAddress> 
</organizer> 
</ns0:Event> 
```

## <a name="next-steps"></a>后续步骤
查看所有[Office 365 适配器](office365-adapters.md)，或安装[功能包 3](https://aka.ms/bts2016fp3)。