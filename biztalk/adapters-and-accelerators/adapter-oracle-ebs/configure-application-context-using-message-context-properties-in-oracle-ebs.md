---
title: 配置 Oracle E-business Suite 中使用消息上下文属性的应用程序上下文 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 51b76788-5c81-4bb4-8ef6-b1439955ea97
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 71920920c11028adb1f699e3faee463876399b36
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003998"
---
# <a name="configure-the-application-context-using-message-context-properties-in-oracle-e-business-suite"></a>配置 Oracle E-business Suite 中使用消息上下文属性的应用程序上下文
若要使用的 Oracle E-business Suite 项目上执行操作[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，必须正确设置应用程序上下文。 可以按以下方式来设置应用程序上下文：  
  
- 通过指定适配器公开的绑定属性。 有关详细信息，请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。  
  
- 通过使用该适配器公开的消息上下文属性。 通过使用消息上下文属性中设置应用程序上下文时，必须考虑以下。  
  
  -   可以设置仅对的值**ApplicationShortName**， **OrganizationID**， **ResponsibilityKey**，以及**ResponsibilityName**使用消息上下文属性。 对于用户名和密码，必须使用的绑定属性。 为指定的值**ResponsibilityKey**消息上下文属性将为指定的值重写**ResponsibilityName**消息上下文属性。  
  
  -   如果将应用程序上下文中使用的绑定属性和消息上下文属性，指定为消息上下文属性的值优先，重写指定的绑定属性的值。 但是，例如，如果指定为消息上下文属性，应用程序短名称和组织 ID 并承担相应责任名称作为绑定属性，仅应用程序的短名称的值来自消息上下文属性。 其余部分将选择从相关的绑定属性。  
  
  为什么通过绑定属性来设置应用程序上下文中使用消息上下文属性？ 如果将使用绑定属性的应用程序上下文，WCF 自定义发送端口[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]仅可用于特定组织 ID、 职责范围以及为绑定属性指定的应用程序。 相反，如果使用消息上下文属性，可以配置 Wcf-custom 发送端口"通用"，并在消息级别设置应用程序上下文。  
  
  适配器客户端必须设置消息上下文属性发送到 Oracle E-business Suite 来调用在 Oracle E-business Suite 操作的消息。 中的消息[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]是固定不变。 因此，客户端必须首先从现有的消息，创建一条消息，并对新消息然后设置消息上下文属性。 在本部分中所述的过程，假设调用现有的消息**请求**，并调用新的消息**New_Request**。  
  
## <a name="set-the-message-context-properties-for-biztalk-applications"></a>设置消息的 BizTalk 应用程序的上下文属性  
  
1. 打开 BizTalk 项目中的[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。  
  
2. 在解决方案资源管理器中右键单击**引用**，然后单击**添加引用**。  
  
3. 在**添加引用**对话框中，单击**浏览**选项卡，然后浏览到位置的 BizTalk 属性架构 DLL 的[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]可用。  
  
    此 DLL `Microsoft.Adapters.OracleEBS.BiztalkPropertySchema.dll`，通过安装[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]处\<*安装驱动器*\>: \Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\bin。  
  
4. 选择 DLL，然后依次**添加**。  
  
5. 在 BizTalk 业务流程中，添加一条消息， **New_Request**。 有关**消息类型**属性，请确保为现有的请求消息选择相同的类型。  
  
6. 在发送形状之前使用该消息发送到发送端口中，添加构造消息形状，并在其中，消息赋值形状。  
  
7. 双击消息赋值形状以打开**BizTalk 表达式编辑器**。  
  
8. 在中**BizTalk 表达式编辑器**，添加以下内容，并单击**确定**:  
  
   ```  
   New_Request = Request;  
   New_Request(Microsoft.Adapters.OracleEBS.BiztalkPropertySchema.ApplicationShortName) = "AR";  
   New_Request(Microsoft.Adapters.OracleEBS.BiztalkPropertySchema.ResponsibilityKey) = "RECEIVABLES_VISION_OPERATIONS";  
   New_Request(Microsoft.Adapters.OracleEBS.BiztalkPropertySchema.ResponsibilityName) = "Receivables, Vision Operations (USA)";  
   New_Request(Microsoft.Adapters.OracleEBS.BiztalkPropertySchema.OrganizationId) = "204";  
   ```  
  
   > [!IMPORTANT]
   >  为指定的值**ResponsibilityKey**消息上下文属性将为指定的值重写**ResponsibilityName**消息上下文属性。  
  
9. 请确保进一步处理的业务流程可通过使用**New_Request**消息。  
  
10. 在可以部署在此业务流程之前[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，必须添加的程序集引用`Microsoft.Adapters.OracleEBS.BiztalkPropertySchema.dll`中要在其中部署业务流程的 BizTalk 应用程序。 若要部署中的程序集[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]:  
  
    1. 启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
    2. 在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，，然后你想要添加 BizTalk 程序集的应用程序。  
  
    3. 右键单击**资源**，依次指向**添加**，然后单击**BizTalk 程序集**。  
  
    4. 在中**添加资源**对话框中，单击**添加**，导航到包含 BizTalk 程序集文件，该文件的文件夹\<*安装驱动器*\>: \Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\bin。 选择`Microsoft.Adapters.OracleEBS.BiztalkPropertySchema.dll`文件，然后依次**打开**。  
  
    5. 上**选项**选项卡上，为 BizTalk 程序集安装到全局程序集缓存 (GAC) 中，指定选项，然后单击**确定**。  
  
## <a name="set-the-language-for-performing-operations"></a>设置执行操作的语言  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]支持 Oracle E-business Suite 的多语言支持 (MLS) 功能，并允许您执行操作时指定的语言。 该适配器公开**语言**消息上下文属性来指定一种语言来执行操作。  
  
 为指定的值**语言**消息上下文属性将重写的值**语言**下的属性绑定**MlsSettings**属性绑定。 有关详细信息**MlsSettings**绑定属性，请参阅[了解关于 BizTalk Adapter for Oracle E-business Suite 绑定属性](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。  
  
