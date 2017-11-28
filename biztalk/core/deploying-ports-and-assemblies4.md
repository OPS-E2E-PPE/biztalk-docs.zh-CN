---
title: "部署端口和 Assemblies4 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying assemblies
- ports, deploying
- Deployment Wizard
- deploying ports
- assemblies, deploying
- deployment, ports and assemblies
ms.assetid: 5a94a2c8-748c-4d1c-a87e-1cd763565886
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b83df400cba64ee55cab230826bf5bf75b1bca69
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="deploying-ports-and-assemblies"></a><span data-ttu-id="ebe1f-102">部署端口和程序集</span><span class="sxs-lookup"><span data-stu-id="ebe1f-102">Deploying Ports and Assemblies</span></span>
<span data-ttu-id="ebe1f-103">使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，可在目标计算机上复制端口和程序集。</span><span class="sxs-lookup"><span data-stu-id="ebe1f-103">Using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you can duplicate ports and assemblies on a target computer.</span></span> <span data-ttu-id="ebe1f-104">BizTalk Server 将发送端口/接收位置配置导出到一个 XML 文件中。</span><span class="sxs-lookup"><span data-stu-id="ebe1f-104">BizTalk Server exports the send ports/receive location configuration into an XML file.</span></span>  
  
 <span data-ttu-id="ebe1f-105">BizTalk Server 可用于执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="ebe1f-105">You can use BizTalk Server to do the following tasks:</span></span>  
  
-   <span data-ttu-id="ebe1f-106">将 BizTalk Server 程序集部署到 BizTalk 配置数据库或从其删除</span><span class="sxs-lookup"><span data-stu-id="ebe1f-106">Deploy or remove BizTalk Server assemblies in a BizTalk Configuration database</span></span>  
  
-   <span data-ttu-id="ebe1f-107">将程序集安装在全局程序集缓存 (GAC) 中或从其卸载</span><span class="sxs-lookup"><span data-stu-id="ebe1f-107">Install or uninstall the assemblies in the global assembly cache (GAC)</span></span>  
  
-   <span data-ttu-id="ebe1f-108">将 BizTalk Server 程序集绑定信息导入到绑定文件或从其导出</span><span class="sxs-lookup"><span data-stu-id="ebe1f-108">Import or export BizTalk Server assembly binding information to and from binding files</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ebe1f-109">JD Edwards OneWorld 的 Microsoft BizTalk 适配器只要求在源（开发）计算机上具有 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="ebe1f-109">The Microsoft BizTalk Adapter for JD Edwards OneWorld only requires that you have Visual Studio on a source (development) computer.</span></span> <span data-ttu-id="ebe1f-110">在生产计算机上不要求使用 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="ebe1f-110">Visual Studio is not required on the production computer.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ebe1f-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="ebe1f-111">In This Section</span></span>  
  
-   [<span data-ttu-id="ebe1f-112">导入绑定文件</span><span class="sxs-lookup"><span data-stu-id="ebe1f-112">Importing Binding Files</span></span>](../core/importing-binding-files3.md)  
  
-   [<span data-ttu-id="ebe1f-113">部署限制</span><span class="sxs-lookup"><span data-stu-id="ebe1f-113">Deployment Limitations</span></span>](../core/deployment-limitations2.md)