---
title: 使用 Office 365 Outlook 联系人适配器 |Microsoft Docs
description: 在 BizTalk Server 中使用 Office 365 Outlook 联系人适配器发送消息。 若要执行此操作，创建使用 Outlook 适配器的发送端口，并使用示例 XML 消息在 Office 365 Outlook 帐户中创建联系人。
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
ms.openlocfilehash: da423cba141dffa8779c97cef521ade730a3c846
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2018
ms.locfileid: "50752677"
---
# <a name="create-a-contact-using-the-office-365-outlook-contact-adapter---biztalk-server"></a><span data-ttu-id="6019e-104">创建使用 Office 365 Outlook 联系人适配器的 BizTalk Server 的联系人</span><span class="sxs-lookup"><span data-stu-id="6019e-104">Create a contact using the Office 365 Outlook Contact adapter - BizTalk Server</span></span>

<span data-ttu-id="6019e-105">在 BizTalk Server 中使用 Office 365 Outlook 联系人适配器在 Office 365 Outlook 中创建联系人。</span><span class="sxs-lookup"><span data-stu-id="6019e-105">Use the Office 365 Outlook Contact adapter in BizTalk Server to create contacts in your Office 365 Outlook.</span></span>

## <a name="create-a-contact-using-a-send-port"></a><span data-ttu-id="6019e-106">创建一个使用发送端口的联系人</span><span class="sxs-lookup"><span data-stu-id="6019e-106">Create a contact using a send port</span></span>

1. <span data-ttu-id="6019e-107">在 BizTalk Server 管理控制台中，右键单击**发送端口**，选择**新建**，然后选择**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="6019e-107">In the BizTalk Server Administration console, right-click **Send Ports**, select **New**, and select **Static One-way send port**.</span></span>

    <span data-ttu-id="6019e-108">[创建发送端口](../core/how-to-create-a-send-port2.md)提供一些指导。</span><span class="sxs-lookup"><span data-stu-id="6019e-108">[Create a Send Port](../core/how-to-create-a-send-port2.md) provides some guidance.</span></span>

2. <span data-ttu-id="6019e-109">输入**名称**。</span><span class="sxs-lookup"><span data-stu-id="6019e-109">Enter a **Name**.</span></span> <span data-ttu-id="6019e-110">在**传输**，请设置**类型**到**Office 365 Outlook 联系人**，然后选择**配置**。</span><span class="sxs-lookup"><span data-stu-id="6019e-110">In **Transport**, set the **Type** to **Office 365 Outlook Contact**, and select **Configure**.</span></span>

3. <span data-ttu-id="6019e-111">选择**登录...**，并登录到你的 Office 365 帐户。</span><span class="sxs-lookup"><span data-stu-id="6019e-111">Select **Sign in …**, and sign in to your Office 365 Account.</span></span> <span data-ttu-id="6019e-112">该帐户是使用你的电子邮件地址自动填充。</span><span class="sxs-lookup"><span data-stu-id="6019e-112">The account is auto-populated with your email address.</span></span>

4. <span data-ttu-id="6019e-113">允许 BizTalk Server 的访问权限的审批请求：</span><span class="sxs-lookup"><span data-stu-id="6019e-113">Allow BizTalk Server approval for permission to access:</span></span>

    ![Office 365 联系人权限](../core/media/office365-contact-permissions.png)

5. <span data-ttu-id="6019e-115">选择**确定**以保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="6019e-115">Select **Ok** to save your changes.</span></span>

### <a name="test-the-send-port"></a><span data-ttu-id="6019e-116">测试发送端口</span><span class="sxs-lookup"><span data-stu-id="6019e-116">Test the send port</span></span>

<span data-ttu-id="6019e-117">可以使用简单文件接收端口和位置来创建 Office 365 Outlook 联系人适配器上的事件。</span><span class="sxs-lookup"><span data-stu-id="6019e-117">You can use a simple File receive port and location to create an event on your Office 365 Outlook Contact adapter.</span></span>

1. <span data-ttu-id="6019e-118">创建使用文件适配器的接收端口。</span><span class="sxs-lookup"><span data-stu-id="6019e-118">Create a receive port using the File adapter.</span></span> <span data-ttu-id="6019e-119">在你接收位置，则设置**接收文件夹**到**c:\\Temp\\中\\**，并将文件掩码设置为 **\*.xml**.</span><span class="sxs-lookup"><span data-stu-id="6019e-119">Within your receive location,  set the **Receive folder** to **C:\\Temp\\In\\**, and set the file mask to **\*.xml**.</span></span>
2. <span data-ttu-id="6019e-120">在您的 Office 365 Outlook 联系人适配器发送端口属性，设置**筛选器**到`BTS.ReceivePortName == <Receive Port Name>`。</span><span class="sxs-lookup"><span data-stu-id="6019e-120">In your Office 365 Outlook Contact adapter send port properties, set the **Filters** to `BTS.ReceivePortName == <Receive Port Name>`.</span></span>
3. <span data-ttu-id="6019e-121">将以下粘贴到文本编辑器中，并将该文件作为**Office365Contact.xml**。</span><span class="sxs-lookup"><span data-stu-id="6019e-121">Paste the following into a text editor, and save the file as **Office365Contact.xml**.</span></span> <span data-ttu-id="6019e-122">这是您的示例消息。</span><span class="sxs-lookup"><span data-stu-id="6019e-122">This is your sample message.</span></span>

    ```xml
        <ns0:Contact xmlns:ns0="http://schemas.microsoft.com/BizTalk/Office365OutlookContacts/Send">
            <categories>categories_0</categories>
            <categories>categories_1</categories>
            <categories>categories_2</categories>
            <birthday>1999-05-31T13:20:00.000-05:00</birthday>
            <fileAs>fileAs_0</fileAs>
            <displayName>displayName_0</displayName>
            <givenName>givenName_0</givenName>
            <initials>initials_0</initials>
            <middleName>middleName_0</middleName>
            <nickName>nickName_0</nickName>
            <surname>surname_0</surname>
            <title>title_0</title>
            <yomiGivenName>yomiGivenName_0</yomiGivenName>
            <yomiSurname>yomiSurname_0</yomiSurname>
            <yomiCompanyName>yomiCompanyName_0</yomiCompanyName>
            <generation>generation_0</generation>
            <jobTitle>jobTitle_0</jobTitle>
            <companyName>companyName_0</companyName>
            <department>department_0</department>
            <officeLocation>officeLocation_0</officeLocation>
            <profession>profession_0</profession>
            <businessHomePage>businessHomePage_0</businessHomePage>
            <assistantName>assistantName_0</assistantName>
            <manager>manager_0</manager>
            <homePhones>homePhones_0</homePhones>
            <homePhones>homePhones_1</homePhones>
            <mobilePhone>mobilePhone_0</mobilePhone>
            <businessPhones>businessPhones_0</businessPhones>
            <businessPhones>businessPhones_1</businessPhones>
            <spouseName>spouseName_0</spouseName>
            <personalNotes>personalNotes_0</personalNotes>
            <children>children_0</children>
            <children>children_1</children>
            <children>children_2</children>
            <emailAddresses>
                <name>name_0</name>
                <address>address_0</address>
            </emailAddresses>
            <emailAddresses>
                <name>name_0</name>
                <address>address_0</address>
            </emailAddresses>
            <homeAddress>
                <city>city_0</city>
                <countryOrRegion>countryOrRegion_0</countryOrRegion>
                <postalCode>10000</postalCode>
                <state>state_0</state>
                <street>street_0</street>
            </homeAddress>
            <businessAddress>
                <city>city_0</city>
                <countryOrRegion>countryOrRegion_0</countryOrRegion>
                <postalCode>11111</postalCode>
                <state>state_0</state>
                <street>street_0</street>
            </businessAddress>
            <otherAddress>
                <city>city_0</city>
                <countryOrRegion>countryOrRegion_0</countryOrRegion>
                <postalCode>21222</postalCode>
                <state>state_0</state>
                <street>street_0</street>
            </otherAddress>
        </ns0:Contact>
    ```
    <span data-ttu-id="6019e-123">**在 SDK 的一部分提供的 XML 架构 < BizTalk 安装文件夹\\SDK\\架构 >**</span><span class="sxs-lookup"><span data-stu-id="6019e-123">**The XML schema is provided as part of the SDK inside < BizTalk Installation Folder\\SDK\\Schemas >**</span></span>

4. <span data-ttu-id="6019e-124">启动文件接收位置和 Office 365 Outlook 联系人适配器发送端口。</span><span class="sxs-lookup"><span data-stu-id="6019e-124">Start the File receive location and the Office 365 Outlook Contact adapter send port.</span></span>
5. <span data-ttu-id="6019e-125">复制**Office365Contact.xml**到接收文件夹的示例消息 (c:\\Temp\\中\\)。</span><span class="sxs-lookup"><span data-stu-id="6019e-125">Copy **Office365Contact.xml** sample message into the receive folder (C:\\Temp\\In\\).</span></span> <span data-ttu-id="6019e-126">发送端口基于 xml 在 Office 365 Outlook 帐户中创建联系人。</span><span class="sxs-lookup"><span data-stu-id="6019e-126">The send port creates a contact in your Office 365 Outlook account based on the xml.</span></span>

## <a name="next-steps"></a><span data-ttu-id="6019e-127">后续步骤</span><span class="sxs-lookup"><span data-stu-id="6019e-127">Next steps</span></span>
<span data-ttu-id="6019e-128">查看所有[Office 365 适配器](office365-adapters.md)，或安装[功能包 3](https://aka.ms/bts2016fp3)。</span><span class="sxs-lookup"><span data-stu-id="6019e-128">See all the [Office 365 adapters](office365-adapters.md), or install [Feature Pack 3](https://aka.ms/bts2016fp3).</span></span>