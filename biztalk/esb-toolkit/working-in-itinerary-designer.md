---
title: 使用路线设计器 |Microsoft Docs
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
ms.openlocfilehash: 747ce8a750f2b2c775deaa1123a1b6b1d387eafc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999398"
---
# <a name="working-in-itinerary-designer"></a>在路线设计器中工作
创建 Microsoft Visual C# 项目后，可以创建新的路线模型并将现有路线添加到项目。 以下步骤介绍如何创建新的旅行计划中，添加一个现有的路线模型，或更改路线的名称。  
  
> [!NOTE]
>  使用路线设计器之前, 必须安装 Microsoft.Practices.ESB.CORE Windows Installer （.msi 文件） 从[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]安装文件夹。 此步骤中将所需的运行时程序集安装到全局程序集缓存中。  
  
## <a name="basic-operations"></a>基本操作  

#### <a name="create-an-itinerary"></a>创建路线  
  
1.  在解决方案资源管理器中右键单击 C# 项目名称，指向**外**，然后单击**新路线**。  
  
2.  在中**名称**框底部的对话框中，键入路线的名称，然后单击**添加**。  
  
    > [!NOTE]
    >  创建新的路线并将其显示在路线设计器中，并创建相应的.itinerary 文件并将其显示在解决方案资源管理器。  
  
#### <a name="add-an-existing-itinerary-to-the-project"></a>向项目添加现有路线
  
1.  在解决方案资源管理器，右键单击 C# 项目名称，指向**外**，然后单击**现有项**。  
  
2.  在中**添加现有项**对话框中，导航到包含路线，单击目录路线，然后依次**添加**。  
  
    > [!NOTE]
    >  路线添加到项目。  
  
#### <a name="change-the-name-of-an-itinerary"></a>更改路线的名称  
  
1.  在解决方案资源管理器，右键单击你想要重命名，然后单击.itinerary 文件**重命名**。  
  
2.  键入新文件名，，然后按 ENTER。  
  
#### <a name="save-an-itinerary"></a>保存路线  
  
上**文件**菜单上，单击**保存\<路线名称\>**。  
  
> [!NOTE]
>  路线文件保存为 DSL 模型中相应的 XML 格式。  
  
#### <a name="set-itinerary-export-properties"></a>设置路线导出属性  
  
1. 在属性窗口中，键入**名称**属性。  
  
2. 在属性窗口中，键入**版本**属性。  
  
3. 在属性窗口中，指定**是请求响应**使用下拉列表的属性。 将此属性设置为 **，则返回 true**如果[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]客户端应用程序的途径与通信使用请求-响应消息交换模式。  
  
4. 在属性窗口中设置**导出模式**属性设置为**默认**或**Strict**。  
  
   > [!NOTE]
   >  创建时[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]使用路线设计器的路线**导出模式**属性可以用于定义该服务将执行的位置。 设置**导出模式**属性设置为**Strict**路线可确保服务在其规定的容器执行; 在这种情况下，XML 路线中的每个路线服务都有阶段属性，指定执行该服务的管道。 如果此属性设置为**默认**、 创建符合 Microsoft ESB 路线时，指定，任何阶段和顺序规定，但不是一定是所需的管道阶段中执行该路线服务。  
  
#### <a name="export-an-itinerary-to-a-file"></a>导出到文件的路线  
  
1.  在属性窗口中，单击**XML 路线导出程序**中**模型导出程序**下拉列表。  
  
2.  在属性窗口中设置**路线 XML 文件**属性的新值。  
  
#### <a name="export-an-itinerary-to-a-database"></a>导出到数据库的路线  
  
1. 在属性窗口中，单击**数据库路线导出程序**中**模型导出程序**下拉列表。  
  
2. 在属性窗口中设置**行程数据库**属性以指向路线的数据库的连接字符串。  
  
3. 在属性窗口中设置**路线状态**属性设置为**已发布**或**已部署**。  
  
   > [!NOTE]
   >  路线拥有的数据库的导出时**路线状态**设置为**已发布**，则不会生效的路线将[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]后的属性设置为运行之前的时间**部署**。  
  
## <a name="security-operations"></a>安全操作  
 使用路线设计器，你可以保护敏感信息，如密码和其他凭据存储在[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]路线，此使用 X.509 证书的信息进行加密。  
  
#### <a name="select-the-x509-certificate-for-an-itinerary"></a>选择一条路线的 X.509 证书  
  
1.  在路线设计器属性窗口中，展开**加密证书**属性，，然后单击**存储区位置**下拉列表，然后选择**CurrentUser**或**LocalMachine**。 这将与当前用户或本地计算机关联的 X.509 证书存储区。  
  
2.  在属性窗口中，单击**存储名称**下拉列表，然后选择对应于你的证书存储的值。  
  
3.  在属性窗口中单击加密证书属性旁边的省略号按钮 （...），然后选择**X.509 证书**中**选择证书**对话框。  
  
#### <a name="remove-the-x509-certificate-from-an-itinerary"></a>从路线中删除的 X.509 证书  
  
- 在路线设计器属性窗口中，展开**加密证书**属性，且然后将设置**存储区位置**属性设置为不同的值。 此取消关联的旧证书[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]路线模型。  
  
#### <a name="disable-the-x509-certificate-validation"></a>禁用 X.509 证书验证  
  
在注册表编辑器中，转到子项**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk ESB Toolkit\2.0\Designer**，然后设置**RequireX509Certificate**属性值设置为**false**。  
  
> [!NOTE]
>  如果您安装了[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]子项是具有 64 位支持的操作系统，在**HKEY_LOCAL_MACHINE\SOFTWARE\SysWOW64\Microsoft\BizTalk ESB Toolkit\2.0\Designer**。