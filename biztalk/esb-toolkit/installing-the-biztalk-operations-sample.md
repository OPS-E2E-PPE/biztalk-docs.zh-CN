---
title: 安装 BizTalk 操作示例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 57c982c2-f796-4c63-9bca-7e8965779850
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23ecf4795c6e495d2606f0411256bd806ee1e6f2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65295142"
---
# <a name="installing-the-biztalk-operations-sample"></a><span data-ttu-id="1e715-102">安装 BizTalk 操作示例</span><span class="sxs-lookup"><span data-stu-id="1e715-102">Installing the BizTalk Operations Sample</span></span>
<span data-ttu-id="1e715-103">Microsoft BizTalk 操作示例需要安装和配置 ESB BizTalk 操作服务。</span><span class="sxs-lookup"><span data-stu-id="1e715-103">The Microsoft BizTalk Operations sample requires the ESB BizTalk Operations service installed and configured.</span></span> <span data-ttu-id="1e715-104">ESB BizTalk 操作服务是可以安装和配置使用 ESB 配置工具的核心 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="1e715-104">ESB BizTalk Operations service is one of the core Web services that can be installed and configured using the ESB Configuration Tool.</span></span> <span data-ttu-id="1e715-105">有关使用 ESB 配置工具的详细信息，请参阅[ http://msdn.microsoft.com/library/jj684558(v=bts.80).aspx ](http://msdn.microsoft.com/library/jj684558\(v=bts.80\).aspx)。</span><span class="sxs-lookup"><span data-stu-id="1e715-105">For more information about using the ESB Configuration Tool, see [http://msdn.microsoft.com/library/jj684558(v=bts.80).aspx](http://msdn.microsoft.com/library/jj684558\(v=bts.80\).aspx).</span></span> <span data-ttu-id="1e715-106">BizTalk 操作 Web 服务的默认位置是<http://localhost/ESB.BizTalkOperationsService/Operations.asmx>; 但是，您可以更改此应用程序配置文件中如果部署中的其他位置或远程服务器的服务。</span><span class="sxs-lookup"><span data-stu-id="1e715-106">The default location of the BizTalk Operations Web service is <http://localhost/ESB.BizTalkOperationsService/Operations.asmx>; however, you can change this in the application configuration file if you deploy the service in a different location or a remote server.</span></span>  

 <span data-ttu-id="1e715-107">你必须从解决方案项目中安装 BizTalk 操作示例。</span><span class="sxs-lookup"><span data-stu-id="1e715-107">You must install BizTalk Operations sample from the solution project.</span></span>  

 <span data-ttu-id="1e715-108">**若要安装 BizTalk 操作示例**</span><span class="sxs-lookup"><span data-stu-id="1e715-108">**To install the BizTalk Operations sample**</span></span>  

1. <span data-ttu-id="1e715-109">打开名为 ESB.BizTalkOperations.Test.Client.csproj 从 \Source\Samples\BizTalkOperations 文件夹安装解决方案[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]到 Visual Studio 中的示例。</span><span class="sxs-lookup"><span data-stu-id="1e715-109">Open the solution named ESB.BizTalkOperations.Test.Client.csproj from the \Source\Samples\BizTalkOperations folder where you installed the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] samples into Visual Studio.</span></span>  

2. <span data-ttu-id="1e715-110">在使用命令**生成**菜单编译解决方案。</span><span class="sxs-lookup"><span data-stu-id="1e715-110">Use the commands on the **Build** menu to compile the solution.</span></span>
