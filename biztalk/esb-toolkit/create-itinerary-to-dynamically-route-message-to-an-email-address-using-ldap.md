---
title: 如何： 创建路线以便动态地将消息路由到电子邮件地址使用的 LDAP 查询 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6d9929dd-5e45-4b0d-90df-52a35e68b0ba
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 93a2237b76524488d7a3903468ebb321d19ae623
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987598"
---
# <a name="how-to-create-an-itinerary-to-dynamically-route-a-message-to-an-email-address-using-an-ldap-query"></a>如何： 创建路线以便动态地将消息路由到电子邮件地址使用的 LDAP 查询
## <a name="goal"></a>目的  
 本部分演示如何创建路线的查询通过 LDAP （轻型目录访问协议） 的电子邮件地址，然后将电子邮件发送到使用 BizTalk Server SMTP 适配器的解析终结点。  
  
 在本操作指南主题中，您将完成以下步骤：  
  
-   创建路线传送名单以动态方式路由消息使用的 LDAP 查询。  
  
-   测试使用路线测试客户端示例应用程序的路线。  
  
## <a name="prerequisites"></a>必要條件  
 本操作指南主题中的过程要求在完成[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)。  
  
 将在其完成本部分中的计算机必须具备 Microsoft Active Directory 目录服务配置并且正在运行 (它不是所需的计算机是域控制器，但必须连接到域)。 此外，SMTP 服务器必须配置并可运行;若要测试本操作指南主题的结果，您必须具有要检查电子邮件发送的 ESB 的客户端。  
  
 在本部分中的说明假定组织名 Global Bank 具有 globalbank.com，域为与 Active Directory 组织单位名为 Employees 的包含的用户 John Evans 具有有效的电子邮件地址在其配置文件 （例如johne@globalbank.com). 不需要复制这些环境因素;但是，为了重新创建此环境中的实现，请考虑这些因素，请根据需要替换项。  
  
## <a name="steps"></a>步骤  
  
#### <a name="to-create-an-esb-itinerary-domain-specific-language-dsl-model"></a>若要创建的 ESB 路线域特定语言 (DSL) 模型  
  
1.  在 Visual Studio 中，打开 C:\HowTos\Patterns\Patterns.sln。  
  
2.  在解决方案资源管理器中右键单击**ItineraryLibrary**项目，指向**添加**，然后单击**新路线**。  
  
3.  在中**添加新项**对话框中，键入**LdapResolution**中**名称**框，并单击**添加**。  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a>若要配置的路线属性  
  
1.  在 Visual Studio 中，单击的设计图面**LdapResolution.itinerary**。 在中**LdapResolution**属性窗口中，配置以下属性：  
  
    1.  在中**模型导出程序**下拉列表中，单击**XML 路线导出程序**。  
  
    2.  下**扩展器设置**部分中下, 一步**路线 XML 文件**属性中，单击省略号按钮 （...）。  
  
    3.  在中**选择 XML 文件**对话框中，键入**C:\HowTos\Itineraries\LdapResolution**中**文件名**框，并单击**保存**。  
  
        > [!NOTE]
        >  此步骤中，可将路线以 XML 形式导出到本地文件位置。 通过为行程数据库，而不导出到本地文件的位置，路线，路线使用 ESB 测试客户端应用程序的测试。 您将完成此过程更高版本的本操作指南主题。  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a>若要定义路线的结构  
  
1. 从工具箱拖动**接入点**至设计图面上的模型元素。 在中**OnRamp1**属性窗口中，配置以下属性：  
  
   1.  单击**名称**属性，并键入**ReceiveNAOrder**。  
  
   2.  在中**Extender**下拉列表中，单击**接入点 ESB 扩展器**。  
  
   3.  在中**BizTalk 应用程序**下拉列表中，单击**Microsoft.Practices.ESB**。  
  
   4.  在中**接收端口**下拉列表中，单击**OnRamp.Itinerary**。  
  
2. 从工具箱拖动**路线服务**模型元素到设计图面，然后将它放到右侧**接入点**模型元素。 在中**ItineraryService1**属性窗口中，配置以下属性：  
  
   1.  单击**名称**属性，并键入**RouteMessageEmail**。  
  
   2.  在**路线服务 Extender**下拉列表中，单击**消息扩展器**。  
  
       > [!NOTE]
       >  此属性定义，过程将花费 （消息传送） 管道中的位置。 或者，如果该过程会发生在业务流程中，设置**路线服务 Extender**属性设置为**业务流程扩展器**。  
  
   3.  在中**容器**下拉列表中，展开**ReceiveNAOrder**，然后单击**接收处理程序**。  
  
   4.  在中**服务名称**下拉列表中，单击**Microsoft.Practices.ESB.Services.Routing**。  
  
3. 右键单击**冲突解决程序**系列**RouteMessageEmail**模型元素，然后单击**添加新解析程序**。 在中**Resolver1**属性窗口中，配置以下属性：  
  
   1.  单击**名称**属性，并键入**LdapResolver**。  
  
   2.  在中**解析程序实现**下拉列表中，单击**LDAP 冲突解决程序扩展**。  
  
   3.  在中**传输名称**下拉列表中，单击**SMTP**。  
  
   4.  单击**传输位置**属性，并键入 **{邮件}**  
  
   5.  单击**SearchRoot**属性，并键入**ou = Employees，dc = globalbank，dc = com**  
  
       > [!NOTE]
       >  如果你未在"先决条件"部分中设置你的环境根据规范，替换上述属性中的值与适用于你的环境。  
  
   6.  单击**筛选器**属性，然后将值更改为 **(&(objectClass=User) (&#124;(givenName = john)))**  
  
       > [!NOTE]
       >  键入前面的值来替换现有文本。  
  
   7.  在中**ThrowErrorIfNotFound**下拉列表中，单击**True**。  
  
4. 在属性窗口中，单击**终结点配置**属性，然后单击省略号按钮 （...）。  
  
   1. 在中**终结点配置**对话框中，单击**EmailBodyText**属性，并键入**顺序已准备好处理**。  
  
   2. 单击**从**属性，并键入<strong>orders@globalbank.com</strong>。  
  
   3. 单击**MessagePartsAttachment**属性，并键入**2**。  
  
   4. 单击**使用者**属性，并键入**顺序 {givenName}**。  
  
   5. 配置**SMTPAuthentication、 SMTPHost、 用户名、** 并**密码**对于本地环境中使用的连接信息的属性。  
  
   6. 单击**确定**以关闭**终结点配置**对话框。  
  
5. 右键单击**LdapResolver**冲突解决程序，并单击**测试解析程序配置**。  
  
6. 在输出窗口中，验证是否已解析中的主题**终结点配置**值是**使 John**，然后验证已解析**传输位置**是电子邮件地址与在 Active Directory 中的用户的帐户相关联 (例如， johne@globalbank.com)。  
  
7. 在工具箱中，单击**连接器**。 将从连接**ReceiveNAOrder**到模型元素**RouteMessageEmail**模型元素。  
  
8. 从工具箱拖动**关闭负载增加**模型元素到设计图面，然后将它放到右侧**RouteMessageEmail**模型元素。 在中**OffRamp1**属性窗口中，配置以下属性：  
  
   1.  单击**名称**属性，并键入**EmailNAOrderDoc**。  
  
   2.  在**Extender**下拉列表中，单击**关闭负载增加 ESB 扩展器**。  
  
   3.  在中**BizTalk 应用程序**下拉列表中，单击**GlobalBank.ESB**。  
  
   4.  在中**发送端口**下拉列表中，单击**DynamicResolutionOneWay**。  
  
9. 从工具箱拖动**路线服务**模型元素到设计图面，然后将其之间放置**RouteMessageEmail**模型元素和**EmailNAOrderDoc**模型元素。 在中**ItineraryService1**属性窗口中，配置以下属性：  
  
    1.  单击**名称**属性，并键入**SendPortFilter**。  
  
    2.  在**路线服务 Extender**下拉列表中，单击**接入点关闭扩展器**。  
  
    3.  在中**关闭负载增加**下拉列表中，展开**EmailNAOrderDoc**，然后单击**发送处理程序**。  
  
10. 在工具箱中，单击**连接器**。 将从连接**RouteMessageEmail**到模型元素**SendPortFilter**模型元素。  
  
11. 在工具箱中，单击**连接器**。 将从连接**SendPortFilter**到模型元素**EmailNAOrderDoc**模型元素。  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a>若要导出与路线测试客户端一起使用的模型  
  
1.  在 Visual Studio 中，右键单击设计图面的**LdapResolution**路线，并单击**导出模型**。  
  
    > [!NOTE]
    >  在 Visual Studio 中打开的 XML 版本的路线。  
  
2.  保存项目的所有项目。  
  
3.  在 Windows 资源管理器，浏览到 C:\HowTos\Itineraries 并请注意，您的路线 XML (LdapResolution.xml) 创建。  
  
#### <a name="to-test-the-itinerary"></a>若要测试路线  
  
1.  打开路线测试客户端示例应用程序使用过程中创建的快捷方式[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB。Itinerary.Test.exe-快捷方式)。  
  
2.  在路线测试客户端，清除**使用 WCF 服务**复选框，然后依次**负载路线**。  
  
3.  在中**打开路线文件**对话框中，浏览到 C:\HowTos\Itineraries。 选择**LdapResolution.xml**，然后单击**打开**加载路线。  
  
4.  单击**确定**清除**成功加载路线**消息。  
  
5.  在路线测试客户端，单击下一步的省略号按钮 （...）**负载消息**框。  
  
6.  在中**选择要加载 XML 文档**对话框中，浏览到 C:\HowTos。 选择**NAOrderDoc.xml**，然后单击**打开**加载测试消息。  
  
7.  单击**提交请求**按钮。 测试完成后，单击**确定**若要消除出现的确认。  
  
8.  打开 Microsoft Outlook Express （或所选的邮件客户端），并验证消息传递到 John Evans 的电子邮件。  
  
## <a name="additional-resources"></a>其他资源  
 有关详细信息，请参阅下列相关主题：  
  
-   [开发活动](../esb-toolkit/development-activities.md)  
  
-   [使用动态解析和路由](../esb-toolkit/using-dynamic-resolution-and-routing.md)