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
ms.openlocfilehash: c56d784362861ad90788e8a3e8dde666dd863efb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65344808"
---
# <a name="guidelines-for-resolving-web-services-permissions-problems"></a>解决 Web Services 权限问题的准则
Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]可广泛使用的 Web 服务使用 SOAP 适配器和业务流程发布为 Web 服务。 本主题提供一些通用准则，最大程度减少 Web services 权限问题和步骤，你可以遵循解决 Web services 权限问题的影响[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
## <a name="general-guidelines"></a>通用指导原则  
  
- **设置用户帐户**:请确保所 IIS 应用程序主机进程标识与之关联的虚拟目录用于承载 Web 服务设置为特定用户帐户，并确保此用户帐户添加到以下组：  
  
  - BizTalk Isolated Host Users （域或本地组）  
  
  - IIS_WPG （本地组）  
  
    这两个组的成员身份所需授予适当的权限来将 SOAP 请求消息发布到 BizTalk MessageBox 数据库，这将激活订阅由 BizTalk Web 服务发布向导创建的 Web 服务业务流程。 有关确定或设置 IIS 应用程序主机进程标识的详细信息，请参阅**设置 IIS 应用程序主机进程标识**一部分[解决IIS权限问题的准则](../core/guidelines-for-resolving-iis-permissions-problems.md).  
  
- **在由 TEMP 环境变量指定的文件夹上设置权限**:确保承载 Web 服务的虚拟目录的 IIS 应用程序主机进程标识具有读取和写入到由 TEMP 环境变量指定的文件夹的权限。 若要确定由 TEMP 环境变量打开指定的文件夹，BizTalk Server 上的命令提示符下键入以下命令，然后按 ENTER:  
  
  ```  
  echo %TEMP%  
  ```  
  
   由 TEMP 环境变量指定的文件夹是 Web 服务的实时 (JIT) 编译为动态链接库 (dll) 文件，因此必须可具有读取和写入权限通过此用户帐户。  
  
- **在 SOAP 方法调用中发送凭据**:请确保 Web 服务客户端在 SOAP 方法调用中发送凭据。 默认情况下，IIS 7.0 中[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]需要 windows 身份验证。 当测试 Web 服务与 Internet Explorer 中，当前登录的用户的凭据会自动发送正因如此，Web 服务可能会从 Internet 资源管理器中工作但却无法在另一个客户端。 如果 Web 服务客户端不会将凭据添加到 SOAP 方法调用将因身份验证失败而生成 SOAP 异常。 有关将凭据发送在 SOAP 方法调用，请参阅中提供的示例代码[如何使用新的 System.Net 类创建 HTTP 客户端](http://support.microsoft.com/kb/303436)。  
  
- **调用 Web 服务的错误故障排除**:如果调用 Web 服务时出现错误，检查应用程序日志，或消息通过 BizTalk Server 管理事件和服务实例跟踪**组中心**页。 有关错误的可能的原因的详细信息，请参阅[监视 BizTalk Server](../core/monitoring-biztalk-server.md)并[使用的组中心页](../core/using-the-group-hub-page.md)。  
  
- **收集调试信息**:若要获取详细的调试信息，请按照主题中所述的步骤[调试已发布 Web Services](../core/debugging-published-web-services.md)如果按照上述步骤无法解决此问题。  
  
## <a name="known-issues"></a>已知问题  
 有关其他信息的已知问题[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]与 Web services 权限相关，请参阅"不能调用作为运行 BizTalk Server 的服务器上的 Web 服务公开的业务流程"网址[ http://go.microsoft.com/fwlink/?LinkId=196379 ](http://go.microsoft.com/fwlink/?LinkId=196379).  
  
## <a name="see-also"></a>请参阅  
 [故障排除的 BizTalk Server 权限](../core/troubleshooting-biztalk-server-permissions.md)   
 [解决 IIS 权限疑难问题的准则](../core/guidelines-for-resolving-iis-permissions-problems.md)