---
title: 安装路线接入点示例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ebe08b84-dc12-4501-8677-15a32e4795a3
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 74bef54370f076d3777f825c89ab828f0f2413d9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65258437"
---
# <a name="installing-the-itinerary-on-ramp-sample"></a>安装路线接入点示例
路线接入点示例依赖于[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]核心解决方案、 动态解析示例和解析程序服务示例。 安装[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]core 自动复制和安装本示例为正确的位置所需的核心程序集。 安装动态解析示例和解析程序服务示例可确保 Web 服务和所使用的路线接入点示例业务规则引擎策略正确安装和配置。  
  
> [!NOTE]
>  必须安装[安装动态解析示例](../esb-toolkit/installing-the-dynamic-resolution-sample.md)并[安装解析程序服务示例](../esb-toolkit/installing-the-resolver-service-sample.md)安装此示例之前。  
>   
>  ESB 示例应用程序位于名为 GlobalBank.ESB 的 Microsoft BizTalk 应用程序。 此外，此示例使用在核心 Microsoft.Practices.ESB 应用程序中安装的项目。 安装路线接入点示例之前，必须添加到 GlobalBank.ESB 应用程序 Microsoft.Practices.ESB 应用程序的引用。  
  
 你可以安装路线接入点示例使用安装脚本中包含[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]。 本节包含下列主题：  
  
-   [使用安装脚本安装路线接入点示例](../esb-toolkit/install-the-itinerary-on-ramp-sample-using-the-install-scripts.md)  
  
-   [路线接入点示例安装的程序集和项目](../esb-toolkit/assemblies-and-artifacts-installed-by-the-itinerary-on-ramp-sample.md)