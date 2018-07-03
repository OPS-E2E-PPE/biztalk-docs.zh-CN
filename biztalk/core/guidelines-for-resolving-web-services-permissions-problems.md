---
title: 解决 Web Services 权限问题的准则 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e29543e9-9b87-437b-ac91-8f1cce01fab4
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dd4420cb7c651ae1ad1bbe4bcb318b86b59c9ac4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005310"
---
# <a name="guidelines-for-resolving-web-services-permissions-problems"></a>解决 Web Services 权限问题的准则
Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]可广泛使用的 Web 服务使用 SOAP 适配器和业务流程发布为 Web 服务。 本主题提供一些通用准则，最大程度减少 Web services 权限问题和步骤，你可以遵循解决 Web services 权限问题的影响[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
## <a name="general-guidelines"></a>通用指导原则  
  
- **设置用户帐户**： 确保与承载 Web 服务的虚拟目录相关联的 IIS 应用程序主机进程标识已设置为特定用户帐户，并确保此用户帐户添加到以下组：  
  
  - BizTalk Isolated Host Users（域组或本地组）  
  
  - IIS_WPG（本地组）  
  
    要向由 BizTalk Web Services 发布向导创建的 Web Services 授予将 SOAP 请求消息发布到 BizTalk MessageBox 数据库中（随后将激活订阅业务流程）的正确权限，必须首先成为这两个组的成员。 有关确定或设置 IIS 应用程序主机进程标识的详细信息，请参阅**设置 IIS 应用程序主机进程标识**一部分[解决IIS权限问题的准则](../core/guidelines-for-resolving-iis-permissions-problems.md).  
  
- **在由 TEMP 环境变量指定的文件夹上设置权限**： 确保承载 Web 服务的虚拟目录的 IIS 应用程序主机进程标识具有读取和写入到指定的文件夹的权限TEMP 环境变量。 若要确定由 TEMP 环境变量指定的文件夹，请在 BizTalk Server 上打开命令提示符，键入以下命令，然后按 Enter：  
  
  ```  
  echo %TEMP%  
  ```  
  
   Web Services 在由 TEMP 环境变量指定的文件夹中实时 (JIT) 编译为动态链接库 (dll) 文件，因而必须由此用户帐户通过读写权限来访问该文件夹。  
  
- **在 SOAP 方法调用中发送凭据**： 确保 Web 服务客户端在 SOAP 方法调用中发送凭据。 默认情况下，IIS 7.0 中[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]需要 windows 身份验证。 当使用 Internet Explorer 测试 Web Services 时，会自动发送当前登录的用户的凭据，这就是 Web Services 可以在 Internet Explorer 中工作但却无法在其他客户端中工作的原因。 如果 Web Services 客户端未将凭据添加到 SOAP 方法调用中，则会由于身份验证失败而产生 SOAP 异常。 有关将凭据发送在 SOAP 方法调用，请参阅中提供的示例代码[如何使用新的 System.Net 类创建 HTTP 客户端](http://support.microsoft.com/kb/303436)。  
  
- **调用 Web 服务的错误故障排除**： 如果调用 Web 服务时出现错误，检查应用程序日志，或消息通过 BizTalk Server 管理事件和服务实例跟踪**组中心**页。 有关错误的可能的原因的详细信息，请参阅[监视 BizTalk Server](../core/monitoring-biztalk-server.md)并[使用的组中心页](../core/using-the-group-hub-page.md)。  
  
- **收集调试信息**： 若要获取详细的调试信息，请按照主题中所述的步骤[调试已发布 Web Services](../core/debugging-published-web-services.md)如果按照上述步骤无法解决此问题。  
  
## <a name="known-issues"></a>已知问题  
 有关其他信息的已知问题[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]与 Web services 权限相关，请参阅"不能调用作为运行 BizTalk Server 的服务器上的 Web 服务公开的业务流程"网址[ http://go.microsoft.com/fwlink/?LinkId=196379 ](http://go.microsoft.com/fwlink/?LinkId=196379).  
  
## <a name="see-also"></a>请参阅  
 [故障排除的 BizTalk Server 权限](../core/troubleshooting-biztalk-server-permissions.md)   
 [解决 IIS 权限疑难问题的准则](../core/guidelines-for-resolving-iis-permissions-problems.md)