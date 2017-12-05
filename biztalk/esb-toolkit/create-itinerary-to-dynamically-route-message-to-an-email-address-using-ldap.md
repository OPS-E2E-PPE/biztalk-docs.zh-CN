---
title: "如何： 创建一条路线动态将一条消息路由到电子邮件地址使用的 LDAP 查询 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6d9929dd-5e45-4b0d-90df-52a35e68b0ba
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 751eaf381b762372652bb77ddf6f00ffe43971c2
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="how-to-create-an-itinerary-to-dynamically-route-a-message-to-an-email-address-using-an-ldap-query"></a>如何： 创建一条路线动态将一条消息路由到使用的 LDAP 查询的电子邮件地址
## <a name="goal"></a>目的  
 本部分演示如何创建一条路线查询通过 LDAP （轻型目录访问协议） 的电子邮件地址，然后将电子邮件发送到使用 BizTalk Server SMTP 适配器解析终结点。  
  
 在本操作方法主题中，你将完成以下步骤：  
  
-   创建动态使用的 LDAP 查询将消息路由路线路由滑动。  
  
-   测试路线使用路线测试客户端示例应用程序。  
  
## <a name="prerequisites"></a>先决条件  
 此操作指南主题中的过程要求在完成[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)。  
  
 将在其完成此部分的计算机必须安装 Microsoft Active Directory 目录服务配置并且正在运行 (它不是所需计算机是域控制器，但必须连接到域)。 此外，SMTP 服务器必须已配置并且正在运行;若要测试本操作指南主题的结果，您必须具有其进行检查 ESB 所发送的电子邮件的客户端。  
  
 本部分中的说明假定组织名全局 Bank globalbank.com，域为使用 Active Directory 组织单位名为 Employees 包含名 John Evans 为使用有效的电子邮件地址 （如其配置文件中的用户johne@globalbank.com). 不需要复制这些环境因素;但是，为了进行重新创建你的环境中的此实现，请考虑这些因素并根据需要替换。  
  
## <a name="steps"></a>步骤  
  
#### <a name="to-create-an-esb-itinerary-domain-specific-language-dsl-model"></a>若要创建 ESB 路线域特定语言 (DSL) 模型  
  
1.  在 Visual Studio 中，打开 C:\HowTos\Patterns\Patterns.sln。  
  
2.  在解决方案资源管理器，右键单击**ItineraryLibrary**项目，指向**添加**，然后单击**新路线**。  
  
3.  在**添加新项**对话框中，键入**LdapResolution**中**名称**框中，并依次**添加**。  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a>若要配置路线的属性  
  
1.  在 Visual Studio 中，单击的设计图面**LdapResolution.itinerary**。 在**LdapResolution**属性窗口中，配置以下属性：  
  
    1.  在**模型导出程序**下拉列表中，单击**XML 路线导出程序**。  
  
    2.  下**扩展程序设置**部分，旁边**路线 XML 文件**属性，单击省略号按钮 （…）。  
  
    3.  在**选择 XML 文件**对话框中，键入**C:\HowTos\Itineraries\LdapResolution**中**文件名**框中，并依次**保存**。  
  
        > [!NOTE]
        >  此步骤允许您路线作为 XML 导出到本地文件位置。 通过到路线的数据库，而不导出到本地文件的位置，一条路线使测试路线使用 ESB 测试客户端应用程序。 你将完成本操作方法主题中后面此过程。  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a>若要定义路线的结构  
  
1.  从工具箱中，拖动**上负载增加**到设计图面上的模型元素。 在**OnRamp1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**ReceiveNAOrder**。  
  
    2.  在**扩展程序**下拉列表中，单击**上负载增加 ESB 扩展程序**。  
  
    3.  在**BizTalk 应用程序**下拉列表中，单击**Microsoft.Practices.ESB**。  
  
    4.  在**接收端口**下拉列表中，单击**OnRamp.Itinerary**。  
  
2.  从工具箱中，拖动**路线服务**模型元素到设计图面，然后将其放到右侧**上负载增加**模型元素。 在**ItineraryService1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**RouteMessageEmail**。  
  
    2.  在**路线服务扩展程序**下拉列表中，单击**消息传送扩展程序**。  
  
        > [!NOTE]
        >  此属性定义的过程将需要在管道 （消息传送） 中的位置。 或者，如果过程将需要一个业务流程中的位置，则设置**路线服务扩展程序**属性**Orchestration 扩展程序**。  
  
    3.  在**容器**下拉列表中，展开**ReceiveNAOrder**，然后单击**接收处理程序**。  
  
    4.  在**服务名称**下拉列表中，单击**Microsoft.Practices.ESB.Services.Routing**。  
  
3.  右键单击**冲突解决程序**集合**RouteMessageEmail**模型元素，并依次**添加新解析程序**。 在**Resolver1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**LdapResolver**。  
  
    2.  在**解析程序实现**下拉列表中，单击**LDAP 冲突解决程序扩展**。  
  
    3.  在**传输名称**下拉列表中，单击**SMTP**。  
  
    4.  单击**传输位置**属性，再然后键入**{邮件}**  
  
    5.  单击**SearchRoot**属性，再然后键入**ou = 员工，dc = globalbank，dc = com**  
  
        > [!NOTE]
        >  如果你未在"先决条件"部分中设置你的环境根据规范，将替换那些适用于你的环境中的上述属性的值。  
  
    6.  单击**筛选器**属性，然后将更改为值**(&(objectClass=User) (&#124;(givenName=john)))**  
  
        > [!NOTE]
        >  键入要替换现有文本的前面的值。  
  
    7.  在**ThrowErrorIfNotFound**下拉列表中，单击**True**。  
  
4.  在属性窗口中，单击**终结点配置**属性，然后单击省略号按钮 （…）。  
  
    1.  在**终结点配置**对话框中，单击**EmailBodyText**属性，再然后键入**顺序已准备好处理**。  
  
    2.  单击**从**属性，再然后键入 **orders@globalbank.com** 。  
  
    3.  单击**MessagePartsAttachment**属性，再然后键入**2**。  
  
    4.  单击**主题**属性，再然后键入**{givenName} 的顺序**。  
  
    5.  配置**SMTPAuthentication、 SMTPHost、 用户名、**和**密码**针对本地环境中使用的连接信息的属性。  
  
    6.  单击**确定**关闭**终结点配置**对话框。  
  
5.  右键单击**LdapResolver**冲突解决程序，，然后单击**测试解析程序配置**。  
  
6.  在输出窗口中，验证中已解析的主题**终结点配置**值是**john 顺序**，然后确认已解析**传输位置**是电子邮件地址与在 Active Directory 中的用户的帐户相关联 (例如， johne@globalbank.com)。  
  
7.  在工具箱中，单击**连接器**。 将从连接**ReceiveNAOrder**到模型元素**RouteMessageEmail**模型元素。  
  
8.  从工具箱中，拖动**关闭负载增加**模型元素到设计图面，然后将其放到右侧**RouteMessageEmail**模型元素。 在**OffRamp1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**EmailNAOrderDoc**。  
  
    2.  在**扩展程序**下拉列表中，单击**关闭负载增加 ESB 扩展程序**。  
  
    3.  在**BizTalk 应用程序**下拉列表中，单击**GlobalBank.ESB**。  
  
    4.  在**发送端口**下拉列表中，单击**DynamicResolutionOneWay**。  
  
9. 从工具箱中，拖动**路线服务**模型元素到设计图面，然后将它之间**RouteMessageEmail**模型元素和**EmailNAOrderDoc**模型元素。 在**ItineraryService1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，再然后键入**SendPortFilter**。  
  
    2.  在**路线服务扩展程序**下拉列表中，单击**关闭负载增加扩展程序**。  
  
    3.  在**关闭负载增加**下拉列表中，展开**EmailNAOrderDoc**，然后单击**发送处理程序**。  
  
10. 在工具箱中，单击**连接器**。 将从连接**RouteMessageEmail**到模型元素**SendPortFilter**模型元素。  
  
11. 在工具箱中，单击**连接器**。 将从连接**SendPortFilter**到模型元素**EmailNAOrderDoc**模型元素。  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a>若要导出与路线测试客户端一起使用的模型  
  
1.  在 Visual Studio 中，右键单击的设计图面**LdapResolution**路线，，然后单击**导出模型**。  
  
    > [!NOTE]
    >  在 Visual Studio 中打开的 XML 版本的路线。  
  
2.  保存所有项目。  
  
3.  在 Windows 资源管理器，浏览到 C:\HowTos\Itineraries，并注意你路线 XML (LdapResolution.xml) 创建。  
  
#### <a name="to-test-the-itinerary"></a>若要测试路线  
  
1.  打开路线测试客户端示例应用程序使用期间创建的快捷方式[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB。Itinerary.Test.exe-快捷方式)。  
  
2.  在路线测试客户端中，清除**使用 WCF 服务**复选框，并依次**负载路线**。  
  
3.  在**打开路线文件**对话框中，浏览到 C:\HowTos\Itineraries。 选择**LdapResolution.xml**，然后单击**打开**加载路线。  
  
4.  单击**确定**清除**成功加载路线**消息。  
  
5.  在路线测试客户端上，单击旁边的省略号按钮 （...）**负载消息**框。  
  
6.  在**选择要加载 XML 文档**对话框中，浏览到 C:\HowTos。 选择**NAOrderDoc.xml**，然后单击**打开**加载测试消息。  
  
7.  单击**提交请求**按钮。 在测试完成后，单击**确定**关闭出现的确认。  
  
8.  打开 Microsoft Outlook Express （或所选邮件客户端） 并验证到 John Evans 的电子邮件的消息传递。  
  
## <a name="additional-resources"></a>其他资源  
 有关详细信息，请参阅下列相关主题：  
  
-   [开发活动](../esb-toolkit/development-activities.md)  
  
-   [使用动态解析和路由](../esb-toolkit/using-dynamic-resolution-and-routing.md)