---
title: 在路线设计器中工作 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 06742cb8-f6d6-46e2-adc0-6be9a3d6a447
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: baf474c68d91b7648f7f0efcfe4e85e7531e4aa1
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25976779"
---
# <a name="working-in-itinerary-designer"></a>在路线设计器中工作
创建一个 Microsoft Visual C# 项目后，可以创建新的路线模型，并将现有路线添加到项目。 以下步骤介绍如何创建新路线、 添加现有路线模型，或更改一条路线的名称。  
  
> [!NOTE]
>  在使用路线设计器之前, 中，你必须安装 Microsoft.Practices.ESB.CORE Windows Installer （.msi 文件） 从[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]安装文件夹。 此步骤将所需的运行时程序集安装到全局程序集缓存中。  
  
## <a name="basic-operations"></a>基本操作  

#### <a name="create-an-itinerary"></a>创建一条路线  
  
1.  在解决方案资源管理器，右键单击 C# 项目名称，指向**添加**，然后单击**新路线**。  
  
2.  在**名称**底部的对话框框中，键入路线的名称，然后单击**添加**。  
  
    > [!NOTE]
    >  创建新的路线并将其显示在路线设计器中，并创建相应的.itinerary 文件并将其显示在解决方案资源管理器。  
  
#### <a name="add-an-existing-itinerary-to-the-project"></a>将现有路线添加到项目
  
1.  在解决方案资源管理器，右键单击 C# 项目名称，指向**添加**，然后单击**现有项**。  
  
2.  在**添加现有项**对话框中，导航到的目录中包含路线，单击路线，，然后单击**添加**。  
  
    > [!NOTE]
    >  路线添加到项目。  
  
#### <a name="change-the-name-of-an-itinerary"></a>更改一条路线的名称  
  
1.  在解决方案资源管理器，右键单击你想要重命名，然后单击.itinerary 文件**重命名**。  
  
2.  键入新的文件名称，，然后按 enter 键。  
  
#### <a name="save-an-itinerary"></a>保存一条路线  
  
上**文件**菜单上，单击**保存\<路线名称\>**。  
  
> [!NOTE]
>  路线文件将保存为相应的 XML 格式的 DSL 模型。  
  
#### <a name="set-itinerary-export-properties"></a>设置路线导出属性  
  
1.  在属性窗口中，键入**名称**属性。  
  
2.  在属性窗口中，键入**版本**属性。  
  
3.  在属性窗口中，指定**是请求响应**使用下拉列表的属性。 将此属性设置为**true**如果[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]客户端应用程序与入口通信使用请求-响应消息交换模式。  
  
4.  在属性窗口中，设置**导出模式**属性**默认**或**Strict**。  
  
    > [!NOTE]
    >  在创建时[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]路线使用路线设计器中，**导出模式**属性可以用于定义该服务将在其中执行。 设置**导出模式**属性**Strict**路线可确保服务在其规定的容器执行; 在这种情况下，XML 行程中的每个路线服务具有阶段属性，指定服务在其中执行的管道。 如果此属性设置为**默认**、 创建与 Microsoft ESB 兼容路线后，指定，没有阶段和路线服务执行顺序规定，但不是一定是所需的管道阶段。  
  
#### <a name="export-an-itinerary-to-a-file"></a>将一条路线导出到文件  
  
1.  在属性窗口中，单击**XML 路线导出程序**中**模型导出程序**下拉列表。  
  
2.  在属性窗口中，设置**路线 XML 文件**属性的新值。  
  
#### <a name="export-an-itinerary-to-a-database"></a>将一条路线导出到数据库  
  
1.  在属性窗口中，单击**数据库路线导出程序**中**模型导出程序**下拉列表。  
  
2.  在属性窗口中，设置**路线数据库**属性连接字符串以指向路线的数据库。  
  
3.  在属性窗口中，设置**路线状态**属性**已发布**或**已部署**。  
  
    > [!NOTE]
    >  当一条路线导出的数据库具有**路线状态**设置为**已发布**、 不生效的路线将[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]后的属性设置为运行花时间**部署**。  
  
## <a name="security-operations"></a>安全操作  
 通过使用路线设计器，你可以保护敏感信息，如密码和其他凭据存储在[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]路线，使用 X.509 证书的此信息进行加密。  
  
#### <a name="select-the-x509-certificate-for-an-itinerary"></a>选择一条路线的 X.509 证书  
  
1.  在路线设计器属性窗口中，展开**加密证书**属性，，然后单击**存储位置**下拉列表，然后选择**CurrentUser**或**LocalMachine**。 这将与当前用户或本地计算机关联的 X.509 证书存储区。  
  
2.  在属性窗口中，单击**存储名称**下拉列表，然后选择对应于你的证书存储的值。  
  
3.  在属性窗口中，单击加密证书属性旁边的省略号按钮 （…），然后选择**X.509 证书**中**选择证书**对话框。  
  
#### <a name="remove-the-x509-certificate-from-an-itinerary"></a>删除一条路线的 X.509 证书  
  
-   在路线设计器属性窗口中，展开**加密证书**属性，且然后将其设置**存储位置**为不同的值的属性。 这解除关联的旧证书[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]路线模型。  
  
#### <a name="disable-the-x509-certificate-validation"></a>禁用 X.509 证书验证  
  
在注册表编辑器中，转到子项**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk ESB Toolkit\2.0\Designer**，然后设置**RequireX509Certificate**属性值设置为**false**。  
  
> [!NOTE]
>  如果你安装[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]子项是 64 位支持的操作系统上, **HKEY_LOCAL_MACHINE\SOFTWARE\SysWOW64\Microsoft\BizTalk ESB Toolkit\2.0\Designer**。