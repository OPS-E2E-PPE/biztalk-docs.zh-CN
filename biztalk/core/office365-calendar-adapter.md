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
# <a name="create-calendar-events-with-the-office-365-outlook-calendar-adapter---biztalk-server"></a><span data-ttu-id="75c69-104">使用 Office 365 Outlook 日历适配器的 BizTalk Server 创建日历事件</span><span class="sxs-lookup"><span data-stu-id="75c69-104">Create calendar events with the Office 365 Outlook Calendar adapter - BizTalk Server</span></span>

<span data-ttu-id="75c69-105">在 BizTalk Server 中使用 Office 365 Outlook 日历适配器创建并接收来自 Office 365 Outlook 日历的日历事件。</span><span class="sxs-lookup"><span data-stu-id="75c69-105">Use the Office 365 Outlook Calendar adapter in BizTalk Server to create and receive calendar events from your Office 365 Outlook Calendar.</span></span>

## <a name="create-events-using-a-send-port"></a><span data-ttu-id="75c69-106">创建事件使用的发送端口</span><span class="sxs-lookup"><span data-stu-id="75c69-106">Create events using a send port</span></span>

1. <span data-ttu-id="75c69-107">在 BizTalk Server 管理控制台中，右键单击**发送端口**，选择**新建**，然后选择**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="75c69-107">In the BizTalk Server Administration console, right-click **Send Ports**, select **New**, and select **Static One-way send port**.</span></span>

    <span data-ttu-id="75c69-108">[创建发送端口](../core/how-to-create-a-send-port2.md)提供一些指导。</span><span class="sxs-lookup"><span data-stu-id="75c69-108">[Create a Send Port](../core/how-to-create-a-send-port2.md) provides some guidance.</span></span>

2. <span data-ttu-id="75c69-109">输入**名称**。</span><span class="sxs-lookup"><span data-stu-id="75c69-109">Enter a **Name**.</span></span> <span data-ttu-id="75c69-110">在**传输**，请设置**类型**到**Office 365 Outlook 日历**，然后选择**配置**。</span><span class="sxs-lookup"><span data-stu-id="75c69-110">In **Transport**, set the **Type** to **Office 365 Outlook Calendar**, and select **Configure**.</span></span>

3. <span data-ttu-id="75c69-111">选择 **[登录...**，并登录到你的 Office 365 帐户。</span><span class="sxs-lookup"><span data-stu-id="75c69-111">Select **[Sign in …**, and sign in to your Office 365 Account.</span></span> <span data-ttu-id="75c69-112">该帐户是使用你的电子邮件地址自动填充。</span><span class="sxs-lookup"><span data-stu-id="75c69-112">The account is auto-populated with your email address.</span></span>

4. <span data-ttu-id="75c69-113">允许 BizTalk Server 的访问权限的审批请求：</span><span class="sxs-lookup"><span data-stu-id="75c69-113">Allow BizTalk Server approval for permission to access:</span></span>

    ![Office 365 日历权限](../core/media/office365-calendar-permissions.png)

5. <span data-ttu-id="75c69-115">配置您 Office365 Outlook 日历的默认属性：</span><span class="sxs-lookup"><span data-stu-id="75c69-115">Configure your Office365 Outlook Calendar default properties:</span></span>

    |<span data-ttu-id="75c69-116">使用此选项</span><span class="sxs-lookup"><span data-stu-id="75c69-116">Use this</span></span>|<span data-ttu-id="75c69-117">执行的操作</span><span class="sxs-lookup"><span data-stu-id="75c69-117">To do this</span></span>|  
    |---|---|  
    | <span data-ttu-id="75c69-118">**日历**</span><span class="sxs-lookup"><span data-stu-id="75c69-118">**Calendar**</span></span> | <span data-ttu-id="75c69-119">选择要在其中创建事件的日历。</span><span class="sxs-lookup"><span data-stu-id="75c69-119">Select the calendar in which events will be created.</span></span> |
    | <span data-ttu-id="75c69-120">**主题**</span><span class="sxs-lookup"><span data-stu-id="75c69-120">**Subject**</span></span> | <span data-ttu-id="75c69-121">设置创建的事件的默认主题。</span><span class="sxs-lookup"><span data-stu-id="75c69-121">Set the default subject for events created.</span></span> <span data-ttu-id="75c69-122">（最多 256 个字符）</span><span class="sxs-lookup"><span data-stu-id="75c69-122">(256 character max)</span></span> |
    | <span data-ttu-id="75c69-123">**必需的与会者**</span><span class="sxs-lookup"><span data-stu-id="75c69-123">**Required Attendees**</span></span> | <span data-ttu-id="75c69-124">输入所需的默认与会者电子邮件地址分隔;。</span><span class="sxs-lookup"><span data-stu-id="75c69-124">Enter your default required attendees email addresses separated by ';'.</span></span> <span data-ttu-id="75c69-125">（最多 256 个字符）</span><span class="sxs-lookup"><span data-stu-id="75c69-125">(256 character max)</span></span> |
    | <span data-ttu-id="75c69-126">**可选与会者**</span><span class="sxs-lookup"><span data-stu-id="75c69-126">**Optional Attendees**</span></span> | <span data-ttu-id="75c69-127">输入可选与会者电子邮件地址分隔应用默认值;。</span><span class="sxs-lookup"><span data-stu-id="75c69-127">Enter your default optional attendees email addresses separated by ';'.</span></span> <span data-ttu-id="75c69-128">（最多 256 个字符）</span><span class="sxs-lookup"><span data-stu-id="75c69-128">(256 character max)</span></span> |

6. <span data-ttu-id="75c69-129">选择日历：</span><span class="sxs-lookup"><span data-stu-id="75c69-129">Select a calendar:</span></span> 

    ![Office 365 日历](../core/media/office365-calendars.png)

    <span data-ttu-id="75c69-131">完成后，您的属性类似于以下：</span><span class="sxs-lookup"><span data-stu-id="75c69-131">When finished, your properties look similar to the following:</span></span>

    ![终结点属性](../core/media/office365-calendar-send-properties.png)

7. <span data-ttu-id="75c69-133">选择**确定**以保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="75c69-133">Select **Ok** to save your changes.</span></span>

### <a name="test-your-send-port"></a><span data-ttu-id="75c69-134">测试您的发送端口</span><span class="sxs-lookup"><span data-stu-id="75c69-134">Test your send port</span></span>

<span data-ttu-id="75c69-135">可以使用简单文件接收端口和位置来创建 Office 365 Outlook 日历上的事件。</span><span class="sxs-lookup"><span data-stu-id="75c69-135">You can use a simple File receive port and location to create an event on your Office 365 Outlook Calendar.</span></span>

1. <span data-ttu-id="75c69-136">创建使用文件适配器的接收端口。</span><span class="sxs-lookup"><span data-stu-id="75c69-136">Create a receive port using the File adapter.</span></span> <span data-ttu-id="75c69-137">在你接收位置，则设置**接收文件夹**到 \**C:\Temp\In\**，并将文件掩码设置为 **\*.xml**。</span><span class="sxs-lookup"><span data-stu-id="75c69-137">Within your receive location,  set the **Receive folder** to \**C:\Temp\In\**, and set the file mask to **\*.xml**.</span></span>
2. <span data-ttu-id="75c69-138">在您的 Office 365 Outlook 日历适配器发送端口属性，设置**筛选器**到`BTS.ReceivePortName == <Receive Port Name>`。</span><span class="sxs-lookup"><span data-stu-id="75c69-138">In your Office 365 Outlook Calendar adapter send port properties, set the **Filters** to `BTS.ReceivePortName == <Receive Port Name>`.</span></span>
3. <span data-ttu-id="75c69-139">将以下粘贴到文本编辑器中，并将该文件作为**Office365Calendar.xml**。</span><span class="sxs-lookup"><span data-stu-id="75c69-139">Paste the following into a text editor, and save the file as **Office365Calendar.xml**.</span></span> <span data-ttu-id="75c69-140">这是您的示例消息。</span><span class="sxs-lookup"><span data-stu-id="75c69-140">This is your sample message.</span></span>

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
    <span data-ttu-id="75c69-141">**在 < BizTalk 安装 Folder\SDK\Schemas > SDK 的一部分提供的 XML 架构**</span><span class="sxs-lookup"><span data-stu-id="75c69-141">**The XML schema is provided as part of the SDK inside < BizTalk Installation Folder\SDK\Schemas >**</span></span>

4. <span data-ttu-id="75c69-142">启动文件接收位置和 Office 365 Outlook 日历适配器发送端口。</span><span class="sxs-lookup"><span data-stu-id="75c69-142">Start the File receive location and the Office 365 Outlook Calendar adapter send port.</span></span>
5. <span data-ttu-id="75c69-143">复制**Office365Calendar.xml**到接收文件夹的示例消息 (C:\Temp\In\)。</span><span class="sxs-lookup"><span data-stu-id="75c69-143">Copy **Office365Calendar.xml** sample message into the receive folder (C:\Temp\In\).</span></span> <span data-ttu-id="75c69-144">发送端口基于 xml 在 Office 365 Outlook 日历中创建的事件。</span><span class="sxs-lookup"><span data-stu-id="75c69-144">The send port creates an event in your Office 365 Outlook calendar based on the xml.</span></span>

## <a name="receive-events-using-a-receive-port"></a><span data-ttu-id="75c69-145">使用接收端口接收事件</span><span class="sxs-lookup"><span data-stu-id="75c69-145">Receive events using a receive port</span></span>

1. <span data-ttu-id="75c69-146">在 BizTalk Server 管理控制台中，右键单击**接收端口**，选择**新建**，然后选择**单向接收端口**。</span><span class="sxs-lookup"><span data-stu-id="75c69-146">In the BizTalk Server Administration console, right-click **Receive Ports**, select **New**, and select **One-Way receive port**.</span></span>

    <span data-ttu-id="75c69-147">[创建接收端口](../core/how-to-create-a-receive-port.md)提供一些指导。</span><span class="sxs-lookup"><span data-stu-id="75c69-147">[Create a receive port](../core/how-to-create-a-receive-port.md) provides some guidance.</span></span>

2. <span data-ttu-id="75c69-148">输入一个名称，并选择**接收位置**。</span><span class="sxs-lookup"><span data-stu-id="75c69-148">Enter a name, and select **Receive Locations**.</span></span>

3. <span data-ttu-id="75c69-149">选择**新建**，并**名称**接收位置。</span><span class="sxs-lookup"><span data-stu-id="75c69-149">Select **New**, and **Name** the receive location.</span></span> <span data-ttu-id="75c69-150">在中**传输**，选择**Office 365 Outlook 日历**从**类型**下拉列表，然后选择**配置**。</span><span class="sxs-lookup"><span data-stu-id="75c69-150">In **Transport**, select **Office 365 Outlook Calendar** from the **Type** drop-down list, and then select **Configure**.</span></span>

4. <span data-ttu-id="75c69-151">选择**登录...**，并登录到你的 Office 365 帐户。</span><span class="sxs-lookup"><span data-stu-id="75c69-151">Select **Sign in …**, and sign in to your Office 365 Account.</span></span> <span data-ttu-id="75c69-152">该帐户是使用你的电子邮件地址自动填充。</span><span class="sxs-lookup"><span data-stu-id="75c69-152">The account is auto-populated with your email address.</span></span>

5. <span data-ttu-id="75c69-153">允许 BizTalk Server 的访问权限的审批请求：</span><span class="sxs-lookup"><span data-stu-id="75c69-153">Allow BizTalk Server approval for permission to access:</span></span>

    ![Office 365 日历权限](../core/media/office365-calendar-permissions.png)

6. <span data-ttu-id="75c69-155">配置**终结点**属性：</span><span class="sxs-lookup"><span data-stu-id="75c69-155">Configure the **Endpoint** properties:</span></span>

    |<span data-ttu-id="75c69-156">使用此选项</span><span class="sxs-lookup"><span data-stu-id="75c69-156">Use this</span></span>|<span data-ttu-id="75c69-157">执行的操作</span><span class="sxs-lookup"><span data-stu-id="75c69-157">To do this</span></span>|  
    |---|---|  
    | <span data-ttu-id="75c69-158">**日历**</span><span class="sxs-lookup"><span data-stu-id="75c69-158">**Calendar**</span></span> | <span data-ttu-id="75c69-159">选择要从其提取事件的日历。</span><span class="sxs-lookup"><span data-stu-id="75c69-159">Select the calendar from which events will be fetched.</span></span>  |
    | <span data-ttu-id="75c69-160">**内开始**</span><span class="sxs-lookup"><span data-stu-id="75c69-160">**Starting within**</span></span> | <span data-ttu-id="75c69-161">选择日历事件必须在其中以接收的 BizTalk （默认值为 15 分钟） 的开始的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="75c69-161">Select the time interval within which a calendar event has to start in order to be received by BizTalk (default is 15 minutes).</span></span>  |

7. <span data-ttu-id="75c69-162">选择一个日历：</span><span class="sxs-lookup"><span data-stu-id="75c69-162">Selecting a calendar:</span></span>

    ![Office 365 日历](../core/media/office365-calendars.png)

    <span data-ttu-id="75c69-164">完成后，您的属性类似于以下：</span><span class="sxs-lookup"><span data-stu-id="75c69-164">When finished, your properties look similar to the following:</span></span>

    ![终结点属性](../core/media/office365-calendar-receive-properties.png)

8. <span data-ttu-id="75c69-166">选择**确定**以保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="75c69-166">Select **Ok** to save your changes.</span></span>

### <a name="test-your-receive-settings"></a><span data-ttu-id="75c69-167">测试在接收设置</span><span class="sxs-lookup"><span data-stu-id="75c69-167">Test your receive settings</span></span>

<span data-ttu-id="75c69-168">可以使用简单的 File 发送端口从 Office 365 Outlook 日历接收消息。</span><span class="sxs-lookup"><span data-stu-id="75c69-168">You can use a simple File send port to receive messages from your Office 365 Outlook Calendar.</span></span>

1. <span data-ttu-id="75c69-169">创建使用文件适配器的发送端口。</span><span class="sxs-lookup"><span data-stu-id="75c69-169">Create a send port using the File adapter.</span></span> <span data-ttu-id="75c69-170">在发送端口的属性，设置**目标文件夹**到 **C:\Temp\Out\**，并将设置和**文件的名称**到 **%MessageID%.xml**.</span><span class="sxs-lookup"><span data-stu-id="75c69-170">Within your send port properties, set the **Destination folder** to **C:\Temp\Out\**, and set the and **File name** to **%MessageID%.xml**.</span></span>
2. <span data-ttu-id="75c69-171">在你的文件将发送端口属性，设置**筛选器**到`BTS.ReceivePortName == <Receive Port Name>`。</span><span class="sxs-lookup"><span data-stu-id="75c69-171">In your File send port properties, set the **Filters** to  `BTS.ReceivePortName == <Receive Port Name>`.</span></span>
3. <span data-ttu-id="75c69-172">启动 Office 365 Outlook 日历接收位置和 File 发送端口。</span><span class="sxs-lookup"><span data-stu-id="75c69-172">Start the Office 365 Outlook Calendar receive location and the File send port.</span></span>
4. <span data-ttu-id="75c69-173">查找目标文件夹 (c:\temp\out) 中的消息。</span><span class="sxs-lookup"><span data-stu-id="75c69-173">Look for messages in the destination folder (c:\temp\out).</span></span> 
<span data-ttu-id="75c69-174">**在 SDK 中包含的 XML 架构`\Program Files (x86)\Microsoft BizTalk Server <your version>\SDK\Schemas`。**</span><span class="sxs-lookup"><span data-stu-id="75c69-174">**The XML schema is included in the SDK at `\Program Files (x86)\Microsoft BizTalk Server <your version>\SDK\Schemas`.**</span></span>

### <a name="example-of-a-received-calendar-event-xml"></a><span data-ttu-id="75c69-175">已接收的日历事件 xml 的示例</span><span class="sxs-lookup"><span data-stu-id="75c69-175">Example of a received calendar event xml</span></span>

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

## <a name="next-steps"></a><span data-ttu-id="75c69-176">后续步骤</span><span class="sxs-lookup"><span data-stu-id="75c69-176">Next steps</span></span>
<span data-ttu-id="75c69-177">查看所有[Office 365 适配器](office365-adapters.md)，或安装[功能包 3](https://aka.ms/bts2016fp3)。</span><span class="sxs-lookup"><span data-stu-id="75c69-177">See all the [Office 365 adapters](office365-adapters.md), or install [Feature Pack 3](https://aka.ms/bts2016fp3).</span></span>