---
title: 附录 b： 安装 SharePoint 适配器 |Microsoft 文档
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
ms.openlocfilehash: 1d0766eabdad71546090b703e41a00f496629d83
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2018
ms.locfileid: "29710832"
---
# <a name="appendix-b-install-the-microsoft-sharepoint-adapter"></a>附录 B：安装 Microsoft SharePoint 适配器
BizTalk Server 包括可以接收消息或将消息发送到 SharePoint 的 SharePoint 适配器。 

[BizTalk Server 2016](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md) 和 [BizTalk Server 2013 R2 / 2013](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2013-and-2013-r2.md) 的软件要求列出了受支持的 SharePoint 版本。

## <a name="sharepoint-adapter-in-biztalk-server-2016"></a>BizTalk Server 2016 中的 SharePoint 适配器

与文件适配器、FTP 适配器和其他现成的适配器相同，BizTalk Server 安装程序会自动安装 CSOM 可再发行组件包。 

SSOM 选项已删除，并且不可用。


## <a name="sharepoint-adapter-in-biztalk-server-2013-and-r2"></a>BizTalk Server 2013 和 R2 中的 SharePoint 适配器
在 BizTalk Server 2013 R2 和 BizTalk Server 2013 中，有两个 SharePoint 适配器选项。

|SharePoint 对象模型|Description|  
|-------------------------|-----------------|  
|CSOM-SharePoint 适配器|**建议**。 与文件适配器、FTP 适配器和其他现成的适配器相同，BizTalk Server 安装程序会自动安装 CSOM 可再发行组件包。 <br/><br/>对 SharePoint 计算机没有任何安装要求。|  
|SSOM - SharePoint Web Service|**已弃用**。 SharePoint 计算机中，运行 BizTalk Server 安装程序，和**仅**选择 SharePoint 适配器。 此安装程序将安装 IIS Web 服务，可处理与 BizTalk Server 上 SharePoint 适配器的通信。 <br/><br/>在大多数环境中，BizTalk Server 和 SharePoint 在不同计算机上。|  

##  <a name="BKMK_Before"></a> 安装之前  

*  SharePoint SSOM 和 CSOM 组件可以同时安装如果同一台计算机上安装 BizTalk Server 2013 R2 或 2013年和 SharePoint。  
  
* BAM 门户仅在 32 位模式下运行。 如果将 BAM 门户安装在 64 位计算机上，请确保已启用 ASP.NET 2.0 32 位并且 IIS 应用程序池处于 32 位模式。 为此，请执行以下操作：  
  
    -   **ASP.NET**：打开 IIS 管理器，单击“BAM 门户”网站，然后双击“处理程序映射”。 在“已启用” 列表中，确认已列出 **PageHandlerFactory-ISAPI-2.0**。  
  
    -   **应用程序池**：打开 IIS 管理器，依次单击“应用程序池”、“BAMAppPool”和“高级设置”。 在 **启用 32 位应用程序**, ，选择 **True**。  
  
* 在安装 SharePoint 时，单击**服务器场**选项，即使你要创建的单一服务器 BizTalk Server 和 SharePoint 安装。 A**服务器场**安装允许你配置 SharePoint 数据库。  
* [CSOM：SharePoint Services 适配器](../core/csom-sharepoint-services-adapter.md)提供了有关配置 SharePoint 接收位置和发送端口的信息。  
* BizTalk Server 2010 及以前版本使用服务器端对象模型 (SSOM) 连接到 SharePoint 2010。 

## <a name="csom-and-ssom-supported-versions"></a>支持 CSOM 和 SSOM 的版本  
SharePoint 支持下表中列出：  
  
||支持 CSOM|支持 SSOM|  
|---|---|---|  
|SharePoint 2016|是|否|  
|SharePoint 2013|是|否|  
|SharePoint Online|是|否|  
|SharePoint 2010|是|是|  
|SharePoint 2007 |否|是|  
  
##  <a name="BKMK_CSOM"></a> 安装 CSOM SharePoint 适配器  
  
1.  基于以下要求使用 SharePoint 计算机：  
  
    ||CSOM 支持|  
    |---|---|  
    |SharePoint 2016<br /><br /> [安装 SharePoint 2016](https://technet.microsoft.com/library/cc262957(v=office.16).aspx)|是|  
    |SharePoint 2013<br /><br /> [安装 SharePoint 2013](https://technet.microsoft.com/library/cc262957.aspx)|是|  
    |SharePoint Online<br /><br /> [SharePoint Online 管理](https://technet.microsoft.com/library/gg132908.aspx)|是|  
    |SharePoint 2010<br /><br /> [安装和部署 SharePoint Server 2010](https://technet.microsoft.com/library/cc262957(v=office.14).aspx)|是|  
    |SharePoint 2007 |否|  
  
2.  在 BizTalk Server 上安装 Windows Identity Foundation：  
  
    | 操作系统 | 信息 |  
    |---|---|  
    |Windows 10、 Windows 8.1、 Windows Server 2016、 Windows Server 2012 和 Windows Server 2012 R2|Windows Identity Foundation 作为“打开或关闭 Windows 功能”中的功能包括在操作系统中。|  
    |Windows Vista SP1|下载位置：[Windows Identity Foundation](http://www.microsoft.com/download/details.aspx?id=17331)。|  
  
3.  安装 BizTalk Server:

    | |  |  
    |---|---|  
     | BizTalk Server 2016 | 运行 BizTalk 安装程序。 |
    | BizTalk Server 2013 R2 | 运行 BizTalk 安装程序，并且**不要**选中“Windows SharePoint Services 适配器”。 |  
    | BizTalk Server 2013 | 运行 BizTalk 安装程序，并且**不要**选中“Windows SharePoint Services 适配器”。 |
  
##  <a name="BKMK_SSOM"></a> 安装 SSOM SharePoint 适配器（已弃用）  
  
1.  使用基于以下 SSOM 要求 SharePoint 计算机：  
  
    ||SSOM 支持|  
    |---|---|  
    |SharePoint 2016<br /><br /> [安装 SharePoint 2016](https://technet.microsoft.com/library/cc262957(v=office.16).aspx)|否| 
    |SharePoint 2013<br /><br /> [安装 SharePoint 2013](http://technet.microsoft.com/library/cc303424.aspx)|否|  
    |SharePoint Online<br /><br /> [SharePoint Online 管理](https://technet.microsoft.com/library/gg132908.aspx)|否|  
    |SharePoint 2010<br /><br /> [安装和部署 SharePoint Server 2010](https://technet.microsoft.com/library/cc262957(v=office.14).aspx)|是|  
    |SharePoint 2007<br /><br /> [安装 SharePoint Server 2007](https://technet.microsoft.com/library/cc262957(v=office.12).aspx) |是|  
  
2.  在 SharePoint 计算机上，配置 SharePoint，和扩展默认网站。 在扩展网站时，会创建一个单独的 IIS 网站，其中包含的内容是相同的，但也提供唯一的 URL 和身份验证类型。  
  
     请参阅 [SharePoint 2010：扩展 Web 应用程序](http://go.microsoft.com/fwlink/p/?LinkId=259124)。  
  
3.  SharePoint 计算机中，运行 BizTalk Server 安装和**仅**检查**Windows SharePoint Services Adapter**。 此时将安装 Web 服务。 **不要运行 BizTalk 配置**。  
  
4.  在 BizTalk Server 中，安装 BizTalk Server。 **不要**选中“Windows SharePoint Services 适配器”。  
  
5.  SharePoint Web 服务 (SSOM) 仅在 64 位模式下运行。 在安装 SharePoint 之前，ASP.NET 和 IIS 应用程序池在 SharePoint 计算机上必须为 64 位模式。 为此，请执行以下操作：  
  
    -   **ASP.NET**：打开 IIS 管理器，单击网站，然后双击“处理程序映射”。 在“已启用”列表中，确认已列出 **PageHandlerFactory-ISAPI-2.0-64**。  
  
    -   **应用程序池**：打开 IIS 管理器，单击“应用程序池”，选择应用程序池，然后单击“高级设置”。 在“启用 32 位应用程序”中，选择“False”。  

