---
title: 使用 Office 365 Outlook 电子邮件适配器 |Microsoft Docs
description: 发送和接收电子邮件消息在 BizTalk Server 中使用 Office 365 Outlook 电子邮件适配器。 若要执行此操作，创建接收端口和发送端口使用的电子邮件适配器，和使用示例消息来测试你的端口。
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
ms.openlocfilehash: daea28056180b436f226fa32b6179bfb1e091f7a
ms.sourcegitcommit: e7609c319b64ec20bf215d17aa5ac4f9dcae52ec
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2018
ms.locfileid: "36946152"
---
# <a name="send-and-receive-email-with-office-365-outlook-email-adapter---biztalk-server"></a><span data-ttu-id="5bc81-104">发送和接收电子邮件与 Office 365 Outlook 电子邮件适配器的 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="5bc81-104">Send and receive email with Office 365 Outlook Email adapter - BizTalk Server</span></span>

<span data-ttu-id="5bc81-105">Office 365 Outlook 电子邮件适配器可以发送和接收邮件从 Office 365 Outlook 电子邮件从 BizTalk。</span><span class="sxs-lookup"><span data-stu-id="5bc81-105">The Office 365 Outlook Email Adapter allows you to send and receive mails from your Office 365 Outlook Email from BizTalk.</span></span>

## <a name="send-mail-using-a-send-port"></a><span data-ttu-id="5bc81-106">使用发送端口发送邮件</span><span class="sxs-lookup"><span data-stu-id="5bc81-106">Send mail using a send port</span></span>

1. <span data-ttu-id="5bc81-107">在 BizTalk Server 管理控制台中，右键单击**发送端口**，选择**新建**，然后选择**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="5bc81-107">In the BizTalk Server Administration console, right-click **Send Ports**, select **New**, and select **Static One-way send port**.</span></span>

    <span data-ttu-id="5bc81-108">[创建发送端口](../core/how-to-create-a-send-port2.md)提供一些指导。</span><span class="sxs-lookup"><span data-stu-id="5bc81-108">[Create a Send Port](../core/how-to-create-a-send-port2.md) provides some guidance.</span></span>

2. <span data-ttu-id="5bc81-109">输入**名称**。</span><span class="sxs-lookup"><span data-stu-id="5bc81-109">Enter a **Name**.</span></span> <span data-ttu-id="5bc81-110">在**传输**，请设置**类型**到**Office 365 Outlook 电子邮件**，然后选择**配置**。</span><span class="sxs-lookup"><span data-stu-id="5bc81-110">In **Transport**, set the **Type** to **Office 365 Outlook Email**, and select **Configure**.</span></span>

3. <span data-ttu-id="5bc81-111">选择**登录...**，并登录到你的 Office 365 帐户。</span><span class="sxs-lookup"><span data-stu-id="5bc81-111">Select **Sign in …**, and sign in to your Office 365 Account.</span></span> <span data-ttu-id="5bc81-112">该帐户是使用你的电子邮件地址自动填充。</span><span class="sxs-lookup"><span data-stu-id="5bc81-112">The account is auto-populated with your email address.</span></span>

4. <span data-ttu-id="5bc81-113">允许 BizTalk Server 的访问权限的审批请求：</span><span class="sxs-lookup"><span data-stu-id="5bc81-113">Allow BizTalk Server approval for permission to access:</span></span>

    ![Office 365 电子邮件权限](../core/media/office365-mail-permissions.png)

5. <span data-ttu-id="5bc81-115">配置您 Office 365 Outlook 电子邮件的默认属性：</span><span class="sxs-lookup"><span data-stu-id="5bc81-115">Configure your Office 365 Outlook Email default properties:</span></span>

    |<span data-ttu-id="5bc81-116">使用此选项</span><span class="sxs-lookup"><span data-stu-id="5bc81-116">Use this</span></span>|<span data-ttu-id="5bc81-117">执行的操作</span><span class="sxs-lookup"><span data-stu-id="5bc81-117">To do this</span></span>|  
    |---|---|  
    | <span data-ttu-id="5bc81-118">**若要**</span><span class="sxs-lookup"><span data-stu-id="5bc81-118">**To**</span></span> | <span data-ttu-id="5bc81-119">指定将默认为分隔的邮件地址 ';'（最多 256 个字符）</span><span class="sxs-lookup"><span data-stu-id="5bc81-119">Specify your default To mail addresses separated by ';' (256 character max)</span></span>|
    | <span data-ttu-id="5bc81-120">CC</span><span class="sxs-lookup"><span data-stu-id="5bc81-120">**CC**</span></span> | <span data-ttu-id="5bc81-121">指定由分隔您默认抄送邮件地址 ';'（最多 256 个字符）</span><span class="sxs-lookup"><span data-stu-id="5bc81-121">Specify your default CC mail addresses separated by ';' (256 character max)</span></span>|
    | <span data-ttu-id="5bc81-122">**主题**</span><span class="sxs-lookup"><span data-stu-id="5bc81-122">**Subject**</span></span> | <span data-ttu-id="5bc81-123">提到你默认邮件主题。</span><span class="sxs-lookup"><span data-stu-id="5bc81-123">Mention your default mail subject.</span></span> <span data-ttu-id="5bc81-124">（最多 256 个字符）</span><span class="sxs-lookup"><span data-stu-id="5bc81-124">(256 character max)</span></span> |
    | <span data-ttu-id="5bc81-125">**重要性**</span><span class="sxs-lookup"><span data-stu-id="5bc81-125">**Importance**</span></span> | <span data-ttu-id="5bc81-126">选择你的重要性的值。</span><span class="sxs-lookup"><span data-stu-id="5bc81-126">Select your value of Importance.</span></span> <span data-ttu-id="5bc81-127">下拉列表中包含值**低**，**正常**并**高**与**正常**默认值。</span><span class="sxs-lookup"><span data-stu-id="5bc81-127">Dropdown contains values **Low**, **Normal** and **High** with **Normal** being the default.</span></span> |

    <span data-ttu-id="5bc81-128">完成后，您的属性类似于以下：</span><span class="sxs-lookup"><span data-stu-id="5bc81-128">When finished, your properties look similar to the following:</span></span>

    ![终结点属性](../core/media/office365-mail-send-properties.png)

6. <span data-ttu-id="5bc81-130">选择**确定**以保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="5bc81-130">Select **Ok** to save your changes.</span></span>

### <a name="important-details"></a><span data-ttu-id="5bc81-131">重要详细信息</span><span class="sxs-lookup"><span data-stu-id="5bc81-131">Important details</span></span>

1. <span data-ttu-id="5bc81-132">你只能发送纯文本消息使用的发送适配器。</span><span class="sxs-lookup"><span data-stu-id="5bc81-132">You can only send plain text messages using the send adapter.</span></span>
2. <span data-ttu-id="5bc81-133">此外可能使用升级的属性会更新默认属性：</span><span class="sxs-lookup"><span data-stu-id="5bc81-133">The default properties may also be updated using promoted properties:</span></span>

|<span data-ttu-id="5bc81-134">“属性”</span><span class="sxs-lookup"><span data-stu-id="5bc81-134">Property</span></span>|<span data-ttu-id="5bc81-135">升级的属性</span><span class="sxs-lookup"><span data-stu-id="5bc81-135">Promoted property</span></span>|
|---|---|
| <span data-ttu-id="5bc81-136">**若要**</span><span class="sxs-lookup"><span data-stu-id="5bc81-136">**To**</span></span> | <span data-ttu-id="5bc81-137">OfficeMail.To</span><span class="sxs-lookup"><span data-stu-id="5bc81-137">OfficeMail.To</span></span> |
| <span data-ttu-id="5bc81-138">CC</span><span class="sxs-lookup"><span data-stu-id="5bc81-138">**CC**</span></span> | <span data-ttu-id="5bc81-139">OfficeMail.CC</span><span class="sxs-lookup"><span data-stu-id="5bc81-139">OfficeMail.CC</span></span> |
| <span data-ttu-id="5bc81-140">**主题**</span><span class="sxs-lookup"><span data-stu-id="5bc81-140">**Subject**</span></span> | <span data-ttu-id="5bc81-141">OfficeMail.Subject</span><span class="sxs-lookup"><span data-stu-id="5bc81-141">OfficeMail.Subject</span></span> |
| <span data-ttu-id="5bc81-142">**重要性**</span><span class="sxs-lookup"><span data-stu-id="5bc81-142">**Importance**</span></span> | <span data-ttu-id="5bc81-143">OfficeMail.Importance</span><span class="sxs-lookup"><span data-stu-id="5bc81-143">OfficeMail.Importance</span></span> |

### <a name="test-your-send-port"></a><span data-ttu-id="5bc81-144">测试您的发送端口</span><span class="sxs-lookup"><span data-stu-id="5bc81-144">Test your send port</span></span>

<span data-ttu-id="5bc81-145">可以使用简单文件接收端口和位置将消息发送到 Office 365 Outlook 电子邮件。</span><span class="sxs-lookup"><span data-stu-id="5bc81-145">You can use a simple File receive port and location to send messages to your Office 365 Outlook Email.</span></span>

1. <span data-ttu-id="5bc81-146">创建使用文件适配器的接收端口。</span><span class="sxs-lookup"><span data-stu-id="5bc81-146">Create a receive port using the File adapter.</span></span> <span data-ttu-id="5bc81-147">在你接收位置，则设置**接收文件夹**到 \**C:\Temp\In\**，并将文件掩码设置为 **\*.xml**。</span><span class="sxs-lookup"><span data-stu-id="5bc81-147">Within your receive location, set the **Receive folder** to \**C:\Temp\In\**, and set the file mask to **\*.xml**.</span></span>
2. <span data-ttu-id="5bc81-148">在您的 Office 365 Outlook 电子邮件适配器发送端口属性，设置**筛选器**到`BTS.ReceivePortName == <Receive Port Name>`。</span><span class="sxs-lookup"><span data-stu-id="5bc81-148">In your Office 365 Outlook Email adapter send port properties, set the **Filters** to `BTS.ReceivePortName == <Receive Port Name>`.</span></span>
3. <span data-ttu-id="5bc81-149">将以下粘贴到文本编辑器中，并将该文件作为**Office365Mail.xml**。</span><span class="sxs-lookup"><span data-stu-id="5bc81-149">Paste the following into a text editor, and save the file as **Office365Mail.xml**.</span></span> <span data-ttu-id="5bc81-150">这是您的示例消息。</span><span class="sxs-lookup"><span data-stu-id="5bc81-150">This is your sample message.</span></span>

    ```xml
    <ns0:Root xmlns:ns0="http://BizTalk_Server_Project1.Schema1"> 
        <Record> 
            <Name>BizTalk User</Name> 
            <ID>001</ID> 
        </Record> 
    </ns0:Root> 
    ```

4. <span data-ttu-id="5bc81-151">启动文件接收位置和 Office 365 Outlook 电子邮件适配器发送端口。</span><span class="sxs-lookup"><span data-stu-id="5bc81-151">Start the File receive location and the Office 365 Outlook Email adapter send port.</span></span>
5. <span data-ttu-id="5bc81-152">复制**Office365Mail.xml**到接收文件夹的示例消息 (C:\Temp\In\)。</span><span class="sxs-lookup"><span data-stu-id="5bc81-152">Copy **Office365Mail.xml** sample message into the receive folder (C:\Temp\In\).</span></span> <span data-ttu-id="5bc81-153">发送端口将 XML 文件作为邮件正文发送到 Office 365 Outlook 电子邮件。</span><span class="sxs-lookup"><span data-stu-id="5bc81-153">The send port sends the XML file as mail body to your Office 365 Outlook Email.</span></span>

## <a name="receive-email-using-a-receive-port"></a><span data-ttu-id="5bc81-154">接收电子邮件使用接收端口</span><span class="sxs-lookup"><span data-stu-id="5bc81-154">Receive email using a receive port</span></span>

1. <span data-ttu-id="5bc81-155">在 BizTalk Server 管理控制台中，右键单击**接收端口**，选择**新建**，然后选择**单向接收端口**。</span><span class="sxs-lookup"><span data-stu-id="5bc81-155">In the BizTalk Server Administration console, right-click **Receive Ports**, select **New**, and select **One-Way receive port**.</span></span>

    <span data-ttu-id="5bc81-156">[创建接收端口](../core/how-to-create-a-receive-port.md)提供一些指导。</span><span class="sxs-lookup"><span data-stu-id="5bc81-156">[Create a receive port](../core/how-to-create-a-receive-port.md) provides some guidance.</span></span>

2. <span data-ttu-id="5bc81-157">输入一个名称，并选择**接收位置**。</span><span class="sxs-lookup"><span data-stu-id="5bc81-157">Enter a name, and select **Receive Locations**.</span></span>

3. <span data-ttu-id="5bc81-158">选择**新建**，并**名称**接收位置。</span><span class="sxs-lookup"><span data-stu-id="5bc81-158">Select **New**, and **Name** the receive location.</span></span> <span data-ttu-id="5bc81-159">在中**传输**，选择**Office 365 Outlook 电子邮件**从**类型**下拉列表，然后选择**配置**。</span><span class="sxs-lookup"><span data-stu-id="5bc81-159">In **Transport**, select **Office 365 Outlook Email** from the **Type** drop-down list, and then select **Configure**.</span></span>

4. <span data-ttu-id="5bc81-160">选择 **[登录...**，并登录到你的 Office 365 帐户。</span><span class="sxs-lookup"><span data-stu-id="5bc81-160">Select **[Sign in …**, and sign in to your Office 365 Account.</span></span> <span data-ttu-id="5bc81-161">该帐户是使用你的电子邮件地址自动填充。</span><span class="sxs-lookup"><span data-stu-id="5bc81-161">The account is auto-populated with your email address.</span></span>

5. <span data-ttu-id="5bc81-162">允许 BizTalk Server 的访问权限的审批请求：</span><span class="sxs-lookup"><span data-stu-id="5bc81-162">Allow BizTalk Server approval for permission to access:</span></span>

    ![Office 365 电子邮件权限](../core/media/office365-mail-permissions.png)

6. <span data-ttu-id="5bc81-164">配置**终结点**属性：</span><span class="sxs-lookup"><span data-stu-id="5bc81-164">Configure the **Endpoint** properties:</span></span>

    |<span data-ttu-id="5bc81-165">使用此选项</span><span class="sxs-lookup"><span data-stu-id="5bc81-165">Use this</span></span>|<span data-ttu-id="5bc81-166">执行的操作</span><span class="sxs-lookup"><span data-stu-id="5bc81-166">To do this</span></span>|  
    |---|---|  
    | <span data-ttu-id="5bc81-167">**文件夹**</span><span class="sxs-lookup"><span data-stu-id="5bc81-167">**Folder**</span></span> | <span data-ttu-id="5bc81-168">选择要获取电子邮件的文件夹。</span><span class="sxs-lookup"><span data-stu-id="5bc81-168">Select the folder to get email.</span></span> <span data-ttu-id="5bc81-169">默认文件夹是收件箱。</span><span class="sxs-lookup"><span data-stu-id="5bc81-169">The default folder is Inbox.</span></span> <span data-ttu-id="5bc81-170">请注意文件夹不是递归性质。</span><span class="sxs-lookup"><span data-stu-id="5bc81-170">Note that folders aren’t recursive in nature.</span></span> <span data-ttu-id="5bc81-171">例如，从子文件夹的电子邮件不是检索。</span><span class="sxs-lookup"><span data-stu-id="5bc81-171">For example, email from subfolders aren’t retreived.</span></span> |
    | <span data-ttu-id="5bc81-172">**从启动**</span><span class="sxs-lookup"><span data-stu-id="5bc81-172">**Start from**</span></span> | <span data-ttu-id="5bc81-173">输入如何从 Office 365 接收电子邮件。</span><span class="sxs-lookup"><span data-stu-id="5bc81-173">Enter how email is received from Office 365.</span></span> <span data-ttu-id="5bc81-174">此值指示 receivedTimeStamp 在 Office 365 Outlook 中的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="5bc81-174">This value indicates receivedTimeStamp of an email in Office 365 Outlook.</span></span> <span data-ttu-id="5bc81-175">不是，将接收输入的值较新的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="5bc81-175">Email more recent than the entered values are received.</span></span>  |
    | <span data-ttu-id="5bc81-176">**仅未读的邮件**</span><span class="sxs-lookup"><span data-stu-id="5bc81-176">**Unread mails only**</span></span> | <span data-ttu-id="5bc81-177">勾选此项以读取仅未读电子邮件。</span><span class="sxs-lookup"><span data-stu-id="5bc81-177">Check this to read only unread email.</span></span> <span data-ttu-id="5bc81-178">保留未选中状态，以读取所有的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="5bc81-178">Keep it unchecked to read all email.</span></span> |
    | <span data-ttu-id="5bc81-179">**Post 操作**</span><span class="sxs-lookup"><span data-stu-id="5bc81-179">**Post Action**</span></span> | <span data-ttu-id="5bc81-180">选择要读取一封电子邮件后执行 post 操作。</span><span class="sxs-lookup"><span data-stu-id="5bc81-180">Select a post action to be performed after an email is read.</span></span> <span data-ttu-id="5bc81-181">**无**是默认设置，并通过 BizTalk 接收到电子邮件之后不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="5bc81-181">**None** is the default, and does nothing after email is received by BizTalk.</span></span> <span data-ttu-id="5bc81-182">**标记为已读**所示，BizTalk 收到一封电子邮件后，你的邮箱中的电子邮件被标记为已读。</span><span class="sxs-lookup"><span data-stu-id="5bc81-182">**Mark as read** implies, that after an email is received by BizTalk, the email in your mailbox is marked as read.</span></span> <span data-ttu-id="5bc81-183">**删除**所示，通过 BizTalk 收到一封电子邮件后，会删除您邮箱中的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="5bc81-183">**Delete** implies, that after an email is received by BizTalk, the email in your mailbox is deleted.</span></span> <span data-ttu-id="5bc81-184">最大程度地执行 post 操作。</span><span class="sxs-lookup"><span data-stu-id="5bc81-184">Post actions are performed on a best-effort basis.</span></span>|

    <span data-ttu-id="5bc81-185">完成后，您的属性类似于以下：</span><span class="sxs-lookup"><span data-stu-id="5bc81-185">When finished, your properties look similar to the following:</span></span>

    ![终结点属性](../core/media/office365-mail-receive-properties.png)

7. <span data-ttu-id="5bc81-187">选择**确定**以保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="5bc81-187">Select **Ok** to save your changes.</span></span>

### <a name="test-your-receive-settings"></a><span data-ttu-id="5bc81-188">测试在接收设置</span><span class="sxs-lookup"><span data-stu-id="5bc81-188">Test your receive settings</span></span>

<span data-ttu-id="5bc81-189">可以使用简单的 File 发送端口以接收来自你的 Office 365 Outlook 电子邮件消息。</span><span class="sxs-lookup"><span data-stu-id="5bc81-189">You can use a simple File send port to receive messages from your Office 365 Outlook Email.</span></span>

1. <span data-ttu-id="5bc81-190">创建使用文件适配器的发送端口。</span><span class="sxs-lookup"><span data-stu-id="5bc81-190">Create a send port using the File adapter.</span></span> <span data-ttu-id="5bc81-191">在发送端口的属性，设置**目标文件夹**到 **C:\Temp\Out\*\*，并将设置和**文件的名称\*\*到 **%MessageID%.xml**.</span><span class="sxs-lookup"><span data-stu-id="5bc81-191">Within your send port properties, set the **Destination folder** to \**C:\Temp\Out\**, and set the and **File name** to **%MessageID%.xml**.</span></span>
2. <span data-ttu-id="5bc81-192">在你的文件将发送端口属性，设置**筛选器**到`BTS.ReceivePortName == <Receive Port Name>`。</span><span class="sxs-lookup"><span data-stu-id="5bc81-192">In your File send port properties, set the **Filters** to  `BTS.ReceivePortName == <Receive Port Name>`.</span></span>
3. <span data-ttu-id="5bc81-193">启动 Office 365 Outlook 电子邮件接收位置和 File 发送端口。</span><span class="sxs-lookup"><span data-stu-id="5bc81-193">Start the Office 365 Outlook Email receive location and the File send port.</span></span>
4. <span data-ttu-id="5bc81-194">查找目标文件夹 (c:\temp\out) 中的消息。</span><span class="sxs-lookup"><span data-stu-id="5bc81-194">Look for messages in the destination folder (c:\temp\out).</span></span>

### <a name="promoted-properties-from-receive-pipeline"></a><span data-ttu-id="5bc81-195">接收管道中的升级的属性</span><span class="sxs-lookup"><span data-stu-id="5bc81-195">Promoted Properties from receive pipeline</span></span>

<span data-ttu-id="5bc81-196">默认情况下提升在接收管道的以下属性：</span><span class="sxs-lookup"><span data-stu-id="5bc81-196">The following properties from the Receive Pipeline are promoted by default:</span></span>

|<span data-ttu-id="5bc81-197">属性名称</span><span class="sxs-lookup"><span data-stu-id="5bc81-197">Property Name</span></span>| <span data-ttu-id="5bc81-198">升级的属性</span><span class="sxs-lookup"><span data-stu-id="5bc81-198">Promoted Property</span></span>|
|---|---|
| <span data-ttu-id="5bc81-199">**重要性**</span><span class="sxs-lookup"><span data-stu-id="5bc81-199">**Importance**</span></span> | <span data-ttu-id="5bc81-200">OfficeMail.ReceivedMailImportance</span><span class="sxs-lookup"><span data-stu-id="5bc81-200">OfficeMail.ReceivedMailImportance</span></span> |
| <span data-ttu-id="5bc81-201">**主题**</span><span class="sxs-lookup"><span data-stu-id="5bc81-201">**Subject**</span></span> | <span data-ttu-id="5bc81-202">OfficeMail.ReceivedMailSubject</span><span class="sxs-lookup"><span data-stu-id="5bc81-202">OfficeMail.ReceivedMailSubject</span></span> |
| <span data-ttu-id="5bc81-203">**SenderName**</span><span class="sxs-lookup"><span data-stu-id="5bc81-203">**SenderName**</span></span> | <span data-ttu-id="5bc81-204">OfficeMail.SenderName</span><span class="sxs-lookup"><span data-stu-id="5bc81-204">OfficeMail.SenderName</span></span> |
| <span data-ttu-id="5bc81-205">**输入**</span><span class="sxs-lookup"><span data-stu-id="5bc81-205">**SenderAddress**</span></span> | <span data-ttu-id="5bc81-206">OfficeMail.SenderAddress</span><span class="sxs-lookup"><span data-stu-id="5bc81-206">OfficeMail.SenderAddress</span></span> |
| <span data-ttu-id="5bc81-207">**HasAttachments**</span><span class="sxs-lookup"><span data-stu-id="5bc81-207">**HasAttachments**</span></span>| <span data-ttu-id="5bc81-208">OfficeMail.HasAttachments</span><span class="sxs-lookup"><span data-stu-id="5bc81-208">OfficeMail.HasAttachments</span></span> |

> [!NOTE]
> <span data-ttu-id="5bc81-209">电子邮件的正文内容传递到该消息。</span><span class="sxs-lookup"><span data-stu-id="5bc81-209">Only the body content of the Email is passed through to the message.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5bc81-210">后续步骤</span><span class="sxs-lookup"><span data-stu-id="5bc81-210">Next steps</span></span>
<span data-ttu-id="5bc81-211">查看所有[Office 365 适配器](office365-adapters.md)，或安装[功能包 3](https://aka.ms/bts2016fp3)。</span><span class="sxs-lookup"><span data-stu-id="5bc81-211">See all the [Office 365 adapters](office365-adapters.md), or install [Feature Pack 3](https://aka.ms/bts2016fp3).</span></span>