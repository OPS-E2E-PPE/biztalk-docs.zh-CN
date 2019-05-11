---
title: 附录 B：安装 SharePoint 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f44c6e0a-dcce-4444-8cac-bd403c81a233
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e638eaaf4b677c5fc08e08d608a92ecf75345676
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401495"
---
# <a name="appendix-b-install-the-microsoft-sharepoint-adapter"></a>附录 B：安装 Microsoft SharePoint 适配器
BizTalk Server 包含可以接收消息或将消息发送到 SharePoint 的 SharePoint 适配器。 

软件要求[BizTalk Server 2016](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)并[BizTalk Server 2013 R2 / 2013年](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2013-and-2013-r2.md)列出的受支持的 SharePoint 版本。

## <a name="sharepoint-adapter-in-biztalk-server-2016"></a>BizTalk Server 2016 中的 SharePoint 适配器

BizTalk Server 安装程序会自动安装 CSOM 可再发行组件包，就像文件适配器、 FTP 适配器和其他的箱适配器。 

SSOM 选项已删除，并且不可用。


## <a name="sharepoint-adapter-in-biztalk-server-2013-and-r2"></a>BizTalk Server 2013 和 R2 中的 SharePoint 适配器
在 BizTalk Server 2013 R2 和 BizTalk Server 2013 中，有了 SharePoint 适配器的两个选项。

|SharePoint 对象模型|Description|  
|-------------------------|-----------------|  
|CSOM 的 SharePoint 适配器|**建议**。 BizTalk Server 安装程序会自动安装 CSOM 可再发行组件包，就像文件适配器、 FTP 适配器和其他的箱适配器。 <br/><br/>SharePoint 计算机上的没有安装要求。|  
|SSOM-SharePoint Web 服务|**已弃用**。 在 SharePoint 计算机上运行 BizTalk Server 安装程序，并**仅**选择 SharePoint 适配器。 此安装程序安装用于处理与 BizTalk 服务器上的 SharePoint 适配器通信的 IIS web 服务。 <br/><br/>在大多数环境中，BizTalk Server 和 SharePoint 在不同计算机上。|  

##  <a name="BKMK_Before"></a> 在安装之前  

*  SharePoint SSOM 和 CSOM 组件可以同时安装如果同一台计算机上安装 BizTalk Server 2013 R2 或 2013年和 SharePoint。  
  
* BAM 门户仅在 32 位模式下运行。 如果在 64 位计算机上安装了 BAM 门户，请确保已启用 ASP.NET 2.0 32 位和 IIS 应用程序池处于 32 位模式。 若要执行此操作：  
  
    -   **ASP.NET**:打开 IIS 管理器中，单击**BAM 门户**网站，，然后双击**处理程序映射**。 在中**已启用**列表中，确认**Pagehandlerfactory-isapi-2.0**列出。  
  
    -   **应用程序池**:打开 IIS 管理器中，单击**应用程序池**，单击**BAMAppPool**，然后单击**高级设置**。 在中**启用 32 位应用程序**，选择**True**。  
  
* 安装 SharePoint 时，单击**服务器场**选项，即使你要创建单服务器 BizTalk Server 和 SharePoint 安装。 一个**服务器场**安装允许您配置 SharePoint 数据库。  
* [CSOM:SharePoint Services 适配器](../core/csom-sharepoint-services-adapter.md)信息提供有关配置 SharePoint 接收位置和发送端口。  
* BizTalk Server 2010 及以前版本使用服务器端对象模型 (SSOM) 连接到 SharePoint 2010。 

## <a name="csom-and-ssom-supported-versions"></a>支持 CSOM 和 SSOM 的版本  
下表中列出了 SharePoint 的支持：  
  
||支持 CSOM|支持 SSOM|  
|---|---|---|  
|SharePoint 2016|是|否|  
|SharePoint 2013|是|否|  
|SharePoint Online|是|否|  
|SharePoint 2010|是|是|  
|SharePoint 2007 |否|是|  
  
##  <a name="BKMK_CSOM"></a> 安装 CSOM SharePoint 适配器  
  
1.  使用 SharePoint 计算机根据以下要求：  
  
    ||CSOM 支持|  
    |---|---|  
    |SharePoint 2016<br /><br /> [安装 SharePoint 2016](https://technet.microsoft.com/library/cc262957(v=office.16).aspx)|是|  
    |SharePoint 2013<br /><br /> [安装 SharePoint 2013](https://technet.microsoft.com/library/cc262957.aspx)|是|  
    |SharePoint Online<br /><br /> [SharePoint Online 管理](https://technet.microsoft.com/library/gg132908.aspx)|是|  
    |SharePoint 2010<br /><br /> [安装和部署 SharePoint Server 2010](https://technet.microsoft.com/library/cc262957(v=office.14).aspx)|是|  
    |SharePoint 2007 |否|  
  
2.  BizTalk Server 上安装 Windows Identity Foundation:  
  
    | 操作系统 | T:System.Diagnostics.Switch |  
    |---|---|  
    |Windows 10、 Windows 8.1、 Windows Server 2016、 Windows Server 2012 和 Windows Server 2012 R2|Windows Identity Foundation 作为一项功能是操作系统附带**打开或关闭打开的 Windows 功能**。|  
    |Windows Vista SP1|下载位置[Windows Identity Foundation](http://www.microsoft.com/download/details.aspx?id=17331)。|  
  
3.  安装 BizTalk Server:

    | |  |  
    |---|---|  
     | BizTalk Server 2016 | 运行 BizTalk 安装程序。 |
    | BizTalk Server 2013 R2 | 运行 BizTalk 安装程序，并执行**不**检查**Windows SharePoint Services 适配器**。 |  
    | BizTalk Server 2013 | 运行 BizTalk 安装程序，并执行**不**检查**Windows SharePoint Services 适配器**。 |
  
##  <a name="BKMK_SSOM"></a> 安装 SSOM SharePoint 适配器 （已弃用）  
  
1.  使用基于以下 SSOM 要求 SharePoint 计算机：  
  
    ||SSOM 支持|  
    |---|---|  
    |SharePoint 2016<br /><br /> [安装 SharePoint 2016](https://technet.microsoft.com/library/cc262957(v=office.16).aspx)|否| 
    |SharePoint 2013<br /><br /> [安装 SharePoint 2013](http://technet.microsoft.com/library/cc303424.aspx)|否|  
    |SharePoint Online<br /><br /> [SharePoint Online 管理](https://technet.microsoft.com/library/gg132908.aspx)|否|  
    |SharePoint 2010<br /><br /> [安装和部署 SharePoint Server 2010](https://technet.microsoft.com/library/cc262957(v=office.14).aspx)|是|  
    |SharePoint 2007<br /><br /> [安装 SharePoint Server 2007](https://technet.microsoft.com/library/cc262957(v=office.12).aspx) |是|  
  
2.  在 SharePoint 计算机上，配置 SharePoint，并扩展默认网站。 在扩展 web 站点时，单独的 IIS 网站上创建它包含相同的内容，但还提供了一个唯一的 URL 和身份验证类型。  
  
     请参阅[SharePoint 2010:扩展 Web 应用程序](http://go.microsoft.com/fwlink/p/?LinkId=259124)。  
  
3.  在 SharePoint 计算机上运行 BizTalk Server 安装和**仅**检查**Windows SharePoint Services 适配器**。 这将安装 web 服务。 **不要运行 BizTalk 配置**。  
  
4.  BizTalk Server 上安装 BizTalk Server。 不要**不**检查**Windows SharePoint Services 适配器**。  
  
5.  SharePoint Web 服务 (SSOM) 仅在 64 位模式下运行。 ASP.NET 和 IIS 应用程序池必须是在 SharePoint 计算机上的 64 位模式下安装 SharePoint 之前。 若要执行此操作：  
  
    -   **ASP.NET**:打开 IIS 管理器中，单击网站，并双击**处理程序映射**。 在中**已启用**列表中，确认**PageHandlerFactory ISAPI-2.0 64**列出。  
  
    -   **应用程序池**:打开 IIS 管理器中，单击**应用程序池**，选择应用程序池，然后单击**高级设置**。 在中**启用 32 位应用程序**，选择**False**。  

