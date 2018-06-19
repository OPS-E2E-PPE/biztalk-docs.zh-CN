---
title: 配置在 Oracle E-business Suite 中使用消息上下文属性的应用程序上下文 |Microsoft 文档
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
ms.openlocfilehash: 89f08c50036dd070d51a8685dc4d47ceaa231737
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25962027"
---
# <a name="configure-the-application-context-using-message-context-properties-in-oracle-e-business-suite"></a>配置在 Oracle E-business Suite 中使用消息上下文属性的应用程序上下文
在使用 Oracle E-business Suite 项目上执行操作[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，必须正确设置应用程序上下文。 你可以通过以下方式来设置应用程序上下文：  
  
-   通过指定适配器公开的绑定属性。 有关详细信息，请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。  
  
-   通过使用适配器公开的消息上下文属性。 通过使用消息上下文属性中设置应用程序上下文时，你必须考虑以下。  
  
    -   你可以设置值仅对**ApplicationShortName**，**组织 Id**， **ResponsibilityKey**，和**ResponsibilityName**通过使用消息上下文属性。 对于用户名和密码，必须使用的绑定属性。 为指定的值**ResponsibilityKey**消息上下文属性将为指定的值重写**ResponsibilityName**消息上下文属性。  
  
    -   如果你设置应用程序上下文使用的绑定属性和消息上下文属性，指定消息上下文属性的值优先，并覆盖指定的绑定属性的值。 但是，例如，如果指定为消息上下文属性，应用程序短名称和组织 ID 并承担相应责任名称为绑定属性，仅应用程序短名称的值均从消息上下文属性。 从相关的绑定属性选取其余部分。  
  
 为何使用通过绑定属性设置的应用程序上下文的消息上下文属性？ 如果你设置使用绑定属性的应用程序上下文，则 WCF 自定义发送端口[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]仅可用于特定的组织 ID、 职责范围以及为绑定属性指定的应用程序。 相反，如果你使用的消息上下文属性，你可以配置"泛型"的 WCF 自定义发送端口，并在消息级别设置的应用程序上下文。  
  
 适配器客户端必须设置该消息上下文属性对发送到 Oracle E-business Suite 以调用上 Oracle E-business Suite 操作的消息。 中的消息[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]是不可变。 因此，客户端必须首先从现有的消息中，创建一条消息并将消息上下文属性对新的消息。 有关本节中所述的过程，假定现有消息称为**请求**，新的消息称为**New_Request**。  
  
## <a name="set-the-message-context-properties-for-biztalk-applications"></a>设置该消息，BizTalk 应用程序的上下文属性  
  
1.  打开 BizTalk 项目中的[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。  
  
2.  在解决方案资源管理器，右键单击**引用**，然后单击**添加引用**。  
  
3.  在**添加引用**对话框中，单击**浏览**选项卡上，然后浏览到位置其中 BizTalk 属性架构 DLL 为[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]可用。  
  
     此 DLL， `Microsoft.Adapters.OracleEBS.BiztalkPropertySchema.dll`，通过安装[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]在\<*安装驱动器*\>: files\microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\bin。  
  
4.  选择 DLL，然后单击**添加**。  
  
5.  在 BizTalk 业务流程，添加一条消息， **New_Request**。 有关**消息类型**属性，请确保将相同的类型选择为现有的请求消息。  
  
6.  在发送形状之前使用该消息发送到发送端口中，添加构造消息形状和在其中，消息赋值形状。  
  
7.  双击要打开的消息分配形状**BizTalk 表达式编辑器**。  
  
8.  在**BizTalk 表达式编辑器**，添加以下内容，，然后单击**确定**:  
  
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
  
10. 你可以部署在此业务流程之前[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，必须添加的程序集引用`Microsoft.Adapters.OracleEBS.BiztalkPropertySchema.dll`BizTalk 应用程序将其中部署业务流程中。 若要部署中的程序集[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]:  
  
    1.  启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
    2.  在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后你想要添加 BizTalk 程序集与应用程序。  
  
    3.  右键单击**资源**，指向**添加**，然后单击**BizTalk 程序集**。  
  
    4.  在**添加资源**对话框中，单击**添加**，导航到包含 BizTalk 程序集文件，它是文件夹\<*安装驱动器*\>: Files\microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\bin。 选择`Microsoft.Adapters.OracleEBS.BiztalkPropertySchema.dll`文件，，然后单击**打开**。  
  
    5.  上**选项**选项卡上，指定安装到全局程序集缓存 (GAC) 中，BizTalk 程序集的选项，然后单击**确定**。  
  
## <a name="set-the-language-for-performing-operations"></a>设置执行操作的语言  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]支持 Oracle E-business Suite 的多语言支持 (MLS) 功能，允许你在执行操作时指定一种语言。 适配器公开**语言**消息上下文属性可指定一种语言来执行操作。  
  
 为指定的值**语言**消息上下文属性将重写的值**语言**绑定下的属性**MlsSettings**绑定属性。 有关详细信息**MlsSettings**绑定属性，请参阅[了解针对 Oracle E-business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。  
  
