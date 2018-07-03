---
title: 重复使用 SAP 适配器绑定 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- binding file, definition
- adapter bindings, reusing
ms.assetid: 5748c22f-20a2-4eb9-ad45-a1bef7290802
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b2c6861deeadb602272a172ba6d3068a04bda1ae
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014206"
---
# <a name="reuse-sap-adapter-bindings"></a>重复使用 SAP 适配器绑定
绑定创建一个逻辑终结点 （例如业务流程端口或角色链接） 和物理终结点之间的映射 (如发送和接收端口)。 这样即可在 BizTalk 业务解决方案的不同组件之间进行通信。 使用 BizTalk Server 管理控制台可以创建绑定。  
  
## <a name="what-is-a-binding-file"></a>什么是绑定文件？  
 绑定文件是一个包含作用域中每个 BizTalk 业务流程的 BizTalk 程序集、 应用程序或组的绑定信息的 XML 文件。 绑定文件描述：  
  
- 每个业务流程绑定到主机
  
- 主机的信任级别
  
- 每个设置发送端口、 接收端口、 接收位置，且已配置的参与方
  
  您可以生成绑定文件，并将它们包含的绑定应用到程序集、 应用程序或组。 这避免了必须在不同的部署环境中手动配置绑定，并加快应用程序部署。  
  
绑定文件不自动生成 BizTalk 程序集、 应用程序，或组。 但是，您可以生成绑定文件导出的绑定。 然后可以将绑定文件导入的应用程序或组。  
  
有关绑定和绑定文件的详细信息，请参阅[绑定文件和应用程序部署](../../core/binding-files-and-application-deployment.md)。
  
## <a name="prerequisites"></a>必要條件  
是的成员的帐户登录[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]Administrators 组或 BizTalk Operators 组。 详细了解权限的详细信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。
 
## <a name="export-bindings"></a>导出绑定
本部分介绍如何导出到 XML 文件的 BizTalk 应用程序的绑定。 您然后可以从 XML 文件到另一个 BizTalk 应用程序来导入绑定。 导入绑定将覆盖相同名称的应用程序中的所有现有绑定。 此外可以将绑定添加到应用程序，不会覆盖现有绑定。 导入应用程序添加的绑定会生效。  
  
1. 打开[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
2. 展开**BizTalk 组**，然后展开**应用程序**。  
  
3. 右键单击你想要导出，其的绑定选择应用程序**导出**，然后选择**绑定**。  
  
4. 上**导出绑定**页上，在**导出到文件**，键入要导出绑定到 XML 文件的绝对路径。  
  
    例如，输入 `C:\Bindings\Application1Bindings.Binding1.xml`  
  
5. 确认**导出当前应用程序中的所有绑定**处于选中状态。  
  
6. 若要导出组的所有参与方信息，请选择**导出全局参与方信息**复选框。  
  
7. 选择“确定”。 绑定被导出到 XML 文件中指定的位置。  

## <a name="import-bindings"></a>导入绑定
导入绑定使用 BizTalk Server 管理控制台。
  
1. 打开[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
2. 展开**BizTalk 组**，然后展开**应用程序**。  
  
3. 右键单击您要向其中导入绑定中，选择应用的程序**导入**，然后选择**绑定**。  
  
4. 选择绑定文件，然后选择**打开**。  
  
绑定文件中的项目将写入该应用程序中。 这些项目显示在该应用程序的相应文件夹中。 例如，发送端口导入的绑定显示在下一部分**发送端口**文件夹。  

## <a name="passwords-are-removed"></a>不会保留密码  
出于安全原因，当您导出绑定文件，[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]会从文件删除绑定的密码。 在导入绑定后，必须为发送端口和接收位置重新配置密码，它们才能正常运行。 在的传输属性对话框中配置密码[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台为发送端口或接收位置。 

有关指定用户名和密码的信息，请参阅[配置为 SAP 系统的凭据登录](../../adapters-and-accelerators/adapter-sap/configure-the-sign-in-credentials-for-the-sap-system.md)。

## <a name="see-also"></a>另请参阅
[生成块以创建 SAP 应用程序](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)