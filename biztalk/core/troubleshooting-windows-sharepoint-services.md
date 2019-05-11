---
title: Windows SharePoint Services 故障排除 |Microsoft Docs
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
ms.openlocfilehash: 95d0b833028afdc3c2b560ed60802ff60d6d4046
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65253613"
---
# <a name="troubleshooting-windows-sharepoint-services"></a>Windows SharePoint Services 故障排除
Microsoft [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] Windows SharePoint Services 适配器使用。 本主题介绍与 Windows SharePoint Services 和这些问题的可能解决方法可能会遇到一些已知的问题。  
  
## <a name="known-issues"></a>已知问题  
  
#### <a name="login-failed-for-user-nt-authoritynetwork-service-error-occurs-when-attempting-to-create-content-database"></a>登录失败的用户 NT AUTHORITY\NETWORK SERVICE 错误发生时尝试创建内容数据库  
  
##### <a name="problem"></a>问题  
 当您尝试创建使用 SharePoint 管理中心网站的内容数据库时，将显示如下错误：  
  
 用户 NT AUTHORITY\NETWORK SERVICE 登录失败  
  
##### <a name="cause"></a>原因  
 要连接到数据库的数据库所有者不同于 Windows SharePoint Services 运行的应用程序池标识时，将出现此问题。  
  
##### <a name="resolution"></a>解决方法  
 若要解决此问题，请执行以下操作：  
  
-   网络服务帐户授予 SQL Server 中的"数据库创建"权限。  
  
-   将应用程序池标识帐户更改为 SQL Server 中具有"数据库创建"权限的帐户。  
  
#### <a name="service-unavailable-error-occurs-when-accessing-the-sharepoint-central-administration-web-site"></a>访问 SharePoint 管理中心网站时出现"服务不可用"错误  
  
##### <a name="problem"></a>问题  
 当您尝试打开 SharePoint 管理中心网站时，将显示如下错误：  
  
 服务不可用  
  
##### <a name="cause"></a>原因  
 此错误的最常见原因是应用程序池 （IIS 6.0 或 IIS 7.0） 或宿主 COM + 应用程序 (IIS 5.x) 已停止 SharePoint 管理中心网站站点。 这通常会发生的应用程序池或 COM + 应用程序使用标识配置，但如果指定的用户名和/或密码无效。  
  
##### <a name="resolution"></a>解决方法  
 按照本主题的"设置 IIS 应用程序主机进程标识"部分中的步骤[解决 IIS 权限疑难问题的准则](../core/guidelines-for-resolving-iis-permissions-problems.md)设置相应的主机进程标识。  
  
#### <a name="cannot-connect-to-the-configuration-database-error-occurs-when-attempting-to-extend-and-create-a-content-database"></a>尝试扩展和创建内容数据库时出现"无法连接到配置数据库"错误  
  
##### <a name="problem"></a>问题  
 当尝试扩展并创建使用 SharePoint 管理中心网站的内容数据库时，将显示如下错误：  
  
 无法连接到配置数据库  
  
##### <a name="cause"></a>原因  
 如果正在运行 SharePoint 管理中心网站的应用程序池使用的帐户不具有到 SQL Server 数据库所需的权限，将出现此问题。  
  
##### <a name="resolution"></a>解决方法  
 若要解决此问题，请执行以下操作：  
  
-   授予应用程序池用于在 SQL Server 中的 SharePoint 管理中心 Web 站点"数据库创建"权限的帐户。  
  
-   将应用程序池标识帐户更改为 SQL Server 中具有"数据库创建"权限的帐户。  
  
#### <a name="the-sharepoint-timer-service-service-failed-to-start-error-is-generated-in-the-application-log-after-rebooting-server"></a>重新启动服务器后应用程序日志中生成"SharePoint 定时服务无法启动"错误  
  
##### <a name="problem"></a>问题  
 重新启动服务器之后, 您将看到事件日志中的以下错误：  
  
 SharePoint 定时服务无法启动  
  
 打开 SharePoint 管理中心站点时，还可能会看到以下错误：  
  
 无法连接到 WSS 配置数据库 STS_Config  
  
##### <a name="cause"></a>原因  
 SharePoint 定时服务无法联系时发生此错误[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]后重新启动数据库。 SharePoint 定时服务用于发送通知和执行计划的任务的[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]。 SharePoint 定时服务无法启动的最常见原因是，通过为其用户名称和/或密码不再有效的标识配置用于运行服务的帐户。  
  
##### <a name="resolution"></a>解决方法  
 请确保用户名和密码指定为 SharePoint 定时服务登录帐户正确并且已启动该服务。  
  
## <a name="see-also"></a>请参阅  
 [如何配置 Windows SharePoint Services 虚拟服务器](http://support.microsoft.com/kb/832769)   
 [如何备份和还原使用 Microsoft SQL Server 2000 桌面引擎 (Windows) 的 Windows SharePoint Services 的安装](http://support.microsoft.com/kb/833797)   
 [连接到 Windows SharePoint Services Web 站点时收到"无法连接到配置数据库"错误消息](http://support.microsoft.com/kb/823287)   
 [当您浏览 Windows SharePoint Services 网站时收到"服务不可用"错误消息](http://support.microsoft.com/kb/823552)   
 [管理您的 Windows SharePoint Services 内容数据库时收到"Database < 数据库名称 > 已存在"错误消息](http://support.microsoft.com/kb/828815)