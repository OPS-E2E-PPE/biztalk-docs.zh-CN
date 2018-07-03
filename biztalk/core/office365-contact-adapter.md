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
ms.openlocfilehash: 3185e080be7a4222ac51072506eb9657eb7b1e1b
ms.sourcegitcommit: e7609c319b64ec20bf215d17aa5ac4f9dcae52ec
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2018
ms.locfileid: "36946159"
---
# <a name="create-a-contact-using-the-office-365-outlook-contact-adapter---biztalk-server"></a>创建使用 Office 365 Outlook 联系人适配器的 BizTalk Server 的联系人

在 BizTalk Server 中使用 Office 365 Outlook 联系人适配器在 Office 365 Outlook 中创建联系人。

## <a name="create-a-contact-using-a-send-port"></a>创建一个使用发送端口的联系人

1. 在 BizTalk Server 管理控制台中，右键单击**发送端口**，选择**新建**，然后选择**静态单向发送端口**。

    [创建发送端口](../core/how-to-create-a-send-port2.md)提供一些指导。

2. 输入**名称**。 在**传输**，请设置**类型**到**Office 365 Outlook 联系人**，然后选择**配置**。

3. 选择**登录...**，并登录到你的 Office 365 帐户。 该帐户是使用你的电子邮件地址自动填充。

4. 允许 BizTalk Server 的访问权限的审批请求：

    ![Office 365 联系人权限](../core/media/office365-contact-permissions.png)

5. 选择**确定**以保存所做的更改。

### <a name="test-the-send-port"></a>测试发送端口

可以使用简单文件接收端口和位置来创建 Office 365 Outlook 联系人适配器上的事件。

1. 创建使用文件适配器的接收端口。 在你接收位置，则设置**接收文件夹**到 **C:\Temp\In\**，并将文件掩码设置为 **\*.xml**。
2. 在您的 Office 365 Outlook 联系人适配器发送端口属性，设置**筛选器**到`BTS.ReceivePortName == <Receive Port Name>`。
3. 将以下粘贴到文本编辑器中，并将该文件作为**Office365Contact.xml**。 这是您的示例消息。

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
    **在 < BizTalk 安装 Folder\SDK\Schemas > SDK 的一部分提供的 XML 架构**

4. 启动文件接收位置和 Office 365 Outlook 联系人适配器发送端口。
5. 复制**Office365Contact.xml**到接收文件夹的示例消息 (C:\Temp\In\)。 发送端口基于 xml 在 Office 365 Outlook 帐户中创建联系人。

## <a name="next-steps"></a>后续步骤
查看所有[Office 365 适配器](office365-adapters.md)，或安装[功能包 3](https://aka.ms/bts2016fp3)。