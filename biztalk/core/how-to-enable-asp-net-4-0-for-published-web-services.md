---
title: 如何启用 ASP.NET 4.0 for 发布 Web 服务 |Microsoft 文档
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
ms.openlocfilehash: e68b8eef114828ad181e83ce0c7acd70a5545e0d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254077"
---
# <a name="how-to-enable-aspnet-40-for-published-web-services"></a>如何对已发布的 Web 服务中启用 ASP.NET 4.0
在 IIS 中设置 ASP.Net 版本。

BizTalk Server Web 服务发布向导依赖于使用 ASP.NET，提供包含在.NET Framework 功能。 ASP.Net 版本还包括您选择的.NET CLR 版本。 

本主题演示如何更改.NET CLR 版本。 

## <a name="prerequisites"></a>先决条件

IIS 是附带**Web 服务器 (IIS)** 在操作系统中的角色。 在安装此角色时，还选择 ASP.NET 的较新版本。 
  
## <a name="update-an-application-pool"></a>更新应用程序池
  
1.  打开**Internet Information Services (IIS) 管理器**:

    1. 在**服务器管理器**，选择**工具**。
    2. 选择**Internet Information Services (IIS) 管理器**。
  
2.  展开服务器名称，然后选择**应用程序池**。  
  
3.  选择应用程序池，并打开**基本设置**。  
  
4. 设置 **.NET CLR 版本**与较新版本，然后选择**确定**以保存所做的更改。  

> [!NOTE]
> 你还可以更改 web.config 文件中的版本。
 
## <a name="allow-the-aspnet-extension"></a>允许 ASP.Net 扩展
  
1.  打开**Internet Information Services (IIS) 管理器**:

    1. 在**服务器管理器**，选择**工具**。
    2. 选择**Internet Information Services (IIS) 管理器**。
  
2.  选择服务器名称，然后双击**ISAPI 和 CGI 限制**。  
  
3. 确认 ASP.NET 是**允许**的 32 位和 64 位版本。  
  
## <a name="see-also"></a>另请参阅  
 [规划发布 Web 服务](../core/planning-for-publishing-web-services2.md)