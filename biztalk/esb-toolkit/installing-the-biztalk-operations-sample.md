---
title: "安装 BizTalk 操作示例 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 57c982c2-f796-4c63-9bca-7e8965779850
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6307f9d9e4ff9907bab22efcde0755dbdfdc228b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="installing-the-biztalk-operations-sample"></a>安装 BizTalk 操作示例
Microsoft BizTalk Operations 示例要求 ESB BizTalk Operations 服务安装和配置。 ESB BizTalk Operations 服务是可以安装和配置使用 ESB 配置工具的核心 Web 服务之一。 有关使用 ESB 配置工具的详细信息，请参阅[http://msdn.microsoft.com/library/jj684558(v=bts.80).aspx](http://msdn.microsoft.com/library/jj684558\(v=bts.80\).aspx). BizTalk 操作 Web 服务的默认位置是 http://localhost/ESB.BizTalkOperationsService/Operations.asmx;但是，你可以在应用程序配置文件更改此如果部署中的不同位置或远程服务器的服务。  
  
 从解决方案项目，必须安装 BizTalk 操作示例。  
  
 **若要安装 BizTalk 操作示例**  
  
1.  打开名为 ESB.BizTalkOperations.Test.Client.csproj 从 \Source\Samples\BizTalkOperations 文件夹安装解决方案[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]示例到[!INCLUDE[vs2010](../includes/vs2010-md.md)]。  
  
2.  使用上的命令**生成**菜单以编译该解决方案。