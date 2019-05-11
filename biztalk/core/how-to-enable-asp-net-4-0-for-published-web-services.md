---
title: 如何启用 ASP.NET 4.0 的已发布的 Web 服务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 58646ff2-77a3-49dc-8593-f6e41d85d4f3
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5613e22070b4103eb3744ebb8b7a0d008ca6df1b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65337969"
---
# <a name="how-to-enable-aspnet-40-for-published-web-services"></a>如何为已发布的 Web Services 启用 ASP.NET 4.0
在 IIS 中设置的 ASP.Net 版本。

BizTalk Server Web Services 发布向导依赖于提供 ASP.NET，这是.NET Framework 附带的功能。 包含您选择的.NET CLR 版本的 ASP.Net 版本。 

本主题演示如何更改.NET CLR 版本。 

## <a name="prerequisites"></a>先决条件

IIS 是附带**Web 服务器 (IIS)** 在操作系统中的角色。 在安装此角色时，还可以选择较新版本的 ASP.NET。 
  
## <a name="update-an-application-pool"></a>更新应用程序池
  
1.  打开**Internet Information Services (IIS) 管理器**:

    1. 在中**服务器管理器**，选择**工具**。
    2. 选择**Internet Information Services (IIS) 管理器**。
  
2.  展开服务器名称，然后选择**应用程序池**。  
  
3.  选择应用程序池，并打开**基本设置**。  
  
4. 设置 **.NET CLR 版本**为较新版本，然后选择**确定**以保存所做的更改。  

> [!NOTE]
> 此外可以更改 web.config 文件中的版本。
 
## <a name="allow-the-aspnet-extension"></a>允许使用 ASP.Net 扩展插件
  
1.  打开**Internet Information Services (IIS) 管理器**:

    1. 在中**服务器管理器**，选择**工具**。
    2. 选择**Internet Information Services (IIS) 管理器**。
  
2.  选择服务器名称，然后双击**ISAPI 和 CGI 限制**。  
  
3. 确认 ASP.NET 是否**允许**的 32 位和 64 位版本。  
  
## <a name="see-also"></a>请参阅  
 [规划发布 Web 服务](../core/planning-for-publishing-web-services2.md)