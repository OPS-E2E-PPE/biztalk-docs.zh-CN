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
# <a name="installing-the-biztalk-operations-sample"></a><span data-ttu-id="f5fbf-102">安装 BizTalk 操作示例</span><span class="sxs-lookup"><span data-stu-id="f5fbf-102">Installing the BizTalk Operations Sample</span></span>
<span data-ttu-id="f5fbf-103">Microsoft BizTalk Operations 示例要求 ESB BizTalk Operations 服务安装和配置。</span><span class="sxs-lookup"><span data-stu-id="f5fbf-103">The Microsoft BizTalk Operations sample requires the ESB BizTalk Operations service installed and configured.</span></span> <span data-ttu-id="f5fbf-104">ESB BizTalk Operations 服务是可以安装和配置使用 ESB 配置工具的核心 Web 服务之一。</span><span class="sxs-lookup"><span data-stu-id="f5fbf-104">ESB BizTalk Operations service is one of the core Web services that can be installed and configured using the ESB Configuration Tool.</span></span> <span data-ttu-id="f5fbf-105">有关使用 ESB 配置工具的详细信息，请参阅[http://msdn.microsoft.com/library/jj684558(v=bts.80).aspx](http://msdn.microsoft.com/library/jj684558\(v=bts.80\).aspx).</span><span class="sxs-lookup"><span data-stu-id="f5fbf-105">For more information about using the ESB Configuration Tool, see [http://msdn.microsoft.com/library/jj684558(v=bts.80).aspx](http://msdn.microsoft.com/library/jj684558\(v=bts.80\).aspx).</span></span> <span data-ttu-id="f5fbf-106">BizTalk 操作 Web 服务的默认位置是 http://localhost/ESB.BizTalkOperationsService/Operations.asmx;但是，你可以在应用程序配置文件更改此如果部署中的不同位置或远程服务器的服务。</span><span class="sxs-lookup"><span data-stu-id="f5fbf-106">The default location of the BizTalk Operations Web service is http://localhost/ESB.BizTalkOperationsService/Operations.asmx; however, you can change this in the application configuration file if you deploy the service in a different location or a remote server.</span></span>  
  
 <span data-ttu-id="f5fbf-107">从解决方案项目，必须安装 BizTalk 操作示例。</span><span class="sxs-lookup"><span data-stu-id="f5fbf-107">You must install BizTalk Operations sample from the solution project.</span></span>  
  
 <span data-ttu-id="f5fbf-108">**若要安装 BizTalk 操作示例**</span><span class="sxs-lookup"><span data-stu-id="f5fbf-108">**To install the BizTalk Operations sample**</span></span>  
  
1.  <span data-ttu-id="f5fbf-109">打开名为 ESB.BizTalkOperations.Test.Client.csproj 从 \Source\Samples\BizTalkOperations 文件夹安装解决方案[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]示例到[!INCLUDE[vs2010](../includes/vs2010-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="f5fbf-109">Open the solution named ESB.BizTalkOperations.Test.Client.csproj from the \Source\Samples\BizTalkOperations folder where you installed the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] samples into [!INCLUDE[vs2010](../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="f5fbf-110">使用上的命令**生成**菜单以编译该解决方案。</span><span class="sxs-lookup"><span data-stu-id="f5fbf-110">Use the commands on the **Build** menu to compile the solution.</span></span>