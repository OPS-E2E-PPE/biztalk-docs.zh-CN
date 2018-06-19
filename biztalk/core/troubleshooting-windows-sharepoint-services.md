---
title: 故障排除 Windows SharePoint Services |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9acf9a0d-2c92-4227-80f8-b2d0cca0c232
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 51243216f2adb73454477252c7b54358df229610
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286989"
---
# <a name="troubleshooting-windows-sharepoint-services"></a>故障排除 Windows SharePoint Services
Microsoft[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]由 Windows SharePoint Services 适配器使用。 本主题介绍使用 Windows SharePoint Services 时可能遇到的某些已知问题以及这些问题的可能解决方法。  
  
## <a name="known-issues"></a>已知问题  
  
#### <a name="login-failed-for-user-nt-authoritynetwork-service-error-occurs-when-attempting-to-create-content-database"></a>用户“NT AUTHORITY\NETWORK SERVICE”尝试创建内容数据库时登录失败并出错  
  
##### <a name="problem"></a>问题  
 当您尝试使用 SharePoint 管理中心网站创建内容数据库时，将显示类似于以下内容的错误：  
  
 用户“NT AUTHORITY\NETWORK SERVICE”登录失败  
  
##### <a name="cause"></a>原因  
 当您连接到的数据库的数据库所有者与 Windows SharePoint Services 运行所用的应用程序池标识不同时，将出现这一问题。  
  
##### <a name="resolution"></a>解决方法  
 若要解决此问题，请执行以下操作：  
  
-   向“网络服务”帐户授予 SQL Server 中的“数据库创建”权限。  
  
-   将应用程序池标识帐户更改为在 SQL Server 中具有“数据库创建”权限的帐户。  
  
#### <a name="service-unavailable-error-occurs-when-accessing-the-sharepoint-central-administration-web-site"></a>访问 SharePoint 管理中心网站时出现“服务不可用”错误  
  
##### <a name="problem"></a>问题  
 当您尝试打开 SharePoint 管理中心网站时，将显示类似于以下内容的错误：  
  
 服务不可用  
  
##### <a name="cause"></a>原因  
 此错误的最常见原因是 SharePoint 管理中心网站的应用程序池（IIS 6.0 或 IIS 7.0）或宿主 COM+ 应用程序 (IIS 5.x) 已停止。 如果该应用程序池或 COM+ 应用程序配置了标识，但指定的用户名和/或密码无效，则通常会出现此错误。  
  
##### <a name="resolution"></a>解决方法  
 按照主题的"设置 IIS 应用程序主机进程标识"部分中的步骤[解决 IIS 权限问题的指导原则](../core/guidelines-for-resolving-iis-permissions-problems.md)设置适当的主机进程标识。  
  
#### <a name="cannot-connect-to-the-configuration-database-error-occurs-when-attempting-to-extend-and-create-a-content-database"></a>当尝试扩展和创建内容数据库时，出现“无法连接到配置数据库”错误  
  
##### <a name="problem"></a>问题  
 当您尝试使用 SharePoint 管理中心网站扩展和创建内容数据库时，将显示类似于以下内容的错误：  
  
 无法连接到配置数据库  
  
##### <a name="cause"></a>原因  
 当由正在运行 SharePoint 管理中心网站的应用程序池使用的帐户对 SQL Server 数据库不具备所需的权限时，将出现此错误。  
  
##### <a name="resolution"></a>解决方法  
 若要解决此问题，请执行以下操作：  
  
-   向由应用程序池用于运行 SharePoint 管理中心网站的帐户授予 SQL Server 中的“数据库创建”权限。  
  
-   将应用程序池标识帐户更改为在 SQL Server 中具有“数据库创建”权限的帐户。  
  
#### <a name="the-sharepoint-timer-service-service-failed-to-start-error-is-generated-in-the-application-log-after-rebooting-server"></a>重新启动服务器后，在应用程序日志中生成“SharePoint 定时服务无法启动”错误  
  
##### <a name="problem"></a>问题  
 后重新启动服务器，你将看到事件日志中的以下错误：  
  
 SharePoint 定时服务无法启动  
  
 当您打开 SharePoint 管理中心站点时，您还可以看到以下错误：  
  
 无法连接到 WSS 配置数据库 STS_Config  
  
##### <a name="cause"></a>原因  
 重新启动后，当 SharePoint 定时服务无法与 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 数据库取得联系时，将出现此错误。 SharePoint 定时服务用于为 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 发送通知和执行已计划的任务。 SharePoint 定时服务无法启动的最常见原因是：用于运行此服务的帐户配置了一个标识，而此标识的用户名和/或密码不再有效。  
  
##### <a name="resolution"></a>解决方法  
 确保为 SharePoint 定时服务登录帐户指定的用户名和密码正确无误，并且已启动此服务。  
  
## <a name="see-also"></a>另请参阅  
 [如何配置 Windows SharePoint Services 虚拟服务器](http://support.microsoft.com/kb/832769)   
 [如何备份和还原使用 Microsoft SQL Server 2000 桌面引擎 (Windows) 的 Windows SharePoint Services 的安装](http://support.microsoft.com/kb/833797)   
 [当你连接到你的 Windows SharePoint Services Web 站点收到"无法连接到配置数据库"错误消息](http://support.microsoft.com/kb/823287)   
 [当您浏览 Windows SharePoint Services 网站时，你会收到"服务不可用"错误消息](http://support.microsoft.com/kb/823552)   
 [管理您的 Windows SharePoint Services 内容数据库时收到"已存在数据库 < a s e _ >"错误消息](http://support.microsoft.com/kb/828815)