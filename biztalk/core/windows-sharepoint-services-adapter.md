---
title: Windows SharePoint Services 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Windows SharePoint Services adapters
ms.assetid: cbfc9bf3-912d-4849-ba8c-07a116888bbd
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 974c312aa9eeea2944365695cc4e92b2006d9614
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65240373"
---
# <a name="windows-sharepoint-services-adapter"></a>Windows SharePoint Services 适配器
针对 Microsoft Windows SharePoint Services 的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 适配器可将 BizTalk Server 与 Windows SharePoint Services 和 Microsoft Office 更紧密地集成在一起。 在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 解决方案中使用 Windows SharePoint Services 适配器可为你提供以下功能：  
  
- 通过 Windows SharePoint Services 可方便地查看输入和输出消息。  
  
- 通过使用诸如 Microsoft Office InfoPath 之类的 Office 应用程序可编辑 XML 消息。  
  
- XML 消息与 InfoPath 之间的双向转换。  
  
  [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 适配器包括以下组件：  
  
|                                                                                                       |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|-------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|   CSOM [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 适配器   |                                                       使用 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 客户端对象模型 (CSOM)。 此适配器将随 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 一起安装。 没有其他安装步骤。<br /><br /> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装***自动***安装 SharePoint 客户端对象模型可再发行的也是在可用[ http://go.microsoft.com/fwlink/p/?LinkId=263482 ](http://go.microsoft.com/fwlink/p/?LinkId=263482)。                                                        |
| SSOM [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] Web 服务 | **已弃用**。 使用 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 服务端对象模型 (SSOM)。<br /><br /> 该 Web 服务安装在 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 计算机上，既可以和 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 在同一计算机上，也可以在单独的计算机上。<br /><br /> 若要安装该 Web 服务，请在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 计算机上运行 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 安装，然后检查 **Windows SharePoint Services 适配器**。 |
  
 [附录 b:安装 Microsoft SharePoint 适配器](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)上提供了详细信息[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]安装。  
  
> [!NOTE]
>  当前不支持联合身份验证。 仅支持用户名和密码。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [CSOM:SharePoint Services Adapter](../core/csom-sharepoint-services-adapter.md)  
  
-   [SSOM:SharePoint Services 适配器 Web Services](../core/ssom-sharepoint-services-adapter-web-service.md)  
  
## <a name="see-also"></a>请参阅  
 [使用适配器](../core/using-adapters.md)   
 [开发 BizTalk Server 应用程序](../core/developing-biztalk-server-applications.md)