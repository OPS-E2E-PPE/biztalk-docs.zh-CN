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
ms.openlocfilehash: fa8fb289e5bb7950f9ad8bca3dac98035bada176
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="installing-the-biztalk-operations-sample"></a><span data-ttu-id="80400-102">安装 BizTalk 操作示例</span><span class="sxs-lookup"><span data-stu-id="80400-102">Installing the BizTalk Operations Sample</span></span>
<span data-ttu-id="80400-103">Microsoft BizTalk Operations 示例要求 ESB BizTalk Operations 服务安装和配置。</span><span class="sxs-lookup"><span data-stu-id="80400-103">The Microsoft BizTalk Operations sample requires the ESB BizTalk Operations service installed and configured.</span></span> <span data-ttu-id="80400-104">ESB BizTalk Operations 服务是可以安装和配置使用 ESB 配置工具的核心 Web 服务之一。</span><span class="sxs-lookup"><span data-stu-id="80400-104">ESB BizTalk Operations service is one of the core Web services that can be installed and configured using the ESB Configuration Tool.</span></span> <span data-ttu-id="80400-105">有关使用 ESB 配置工具的详细信息，请参阅[http://msdn.microsoft.com/library/jj684558(v=bts.80).aspx](http://msdn.microsoft.com/library/jj684558\(v=bts.80\).aspx).</span><span class="sxs-lookup"><span data-stu-id="80400-105">For more information about using the ESB Configuration Tool, see [http://msdn.microsoft.com/library/jj684558(v=bts.80).aspx](http://msdn.microsoft.com/library/jj684558\(v=bts.80\).aspx).</span></span> <span data-ttu-id="80400-106">BizTalk 操作 Web 服务的默认位置是 http://localhost/ESB.BizTalkOperationsService/Operations.asmx;但是，你可以在应用程序配置文件更改此如果部署中的不同位置或远程服务器的服务。</span><span class="sxs-lookup"><span data-stu-id="80400-106">The default location of the BizTalk Operations Web service is http://localhost/ESB.BizTalkOperationsService/Operations.asmx; however, you can change this in the application configuration file if you deploy the service in a different location or a remote server.</span></span>  
  
 <span data-ttu-id="80400-107">从解决方案项目，必须安装 BizTalk 操作示例。</span><span class="sxs-lookup"><span data-stu-id="80400-107">You must install BizTalk Operations sample from the solution project.</span></span>  
  
 <span data-ttu-id="80400-108">**若要安装 BizTalk 操作示例**</span><span class="sxs-lookup"><span data-stu-id="80400-108">**To install the BizTalk Operations sample**</span></span>  
  
1.  <span data-ttu-id="80400-109">打开名为 ESB.BizTalkOperations.Test.Client.csproj 从 \Source\Samples\BizTalkOperations 文件夹安装解决方案[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]到 Visual Studio 示例。</span><span class="sxs-lookup"><span data-stu-id="80400-109">Open the solution named ESB.BizTalkOperations.Test.Client.csproj from the \Source\Samples\BizTalkOperations folder where you installed the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] samples into Visual Studio.</span></span>  
  
2.  <span data-ttu-id="80400-110">使用上的命令**生成**菜单以编译该解决方案。</span><span class="sxs-lookup"><span data-stu-id="80400-110">Use the commands on the **Build** menu to compile the solution.</span></span>