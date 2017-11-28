---
title: "查看具有 BizTalk 程序集查看器的程序集 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9831eb88-84bc-4d18-8174-43c3baab83fe
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7567a5fad06137626fa371790778917b2f92a1bb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="viewing-assemblies-with-the-biztalk-assembly-viewer"></a><span data-ttu-id="0617d-102">查看具有 BizTalk 程序集查看器的程序集</span><span class="sxs-lookup"><span data-stu-id="0617d-102">Viewing Assemblies with the BizTalk Assembly Viewer</span></span>
<span data-ttu-id="0617d-103">当开发应用程序或部署程序集时，需要查看部署了哪些程序集以及可以使用哪些程序集。</span><span class="sxs-lookup"><span data-stu-id="0617d-103">When you are developing applications or deploying assemblies, you need to see which assemblies are deployed and available to you.</span></span> <span data-ttu-id="0617d-104">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 为此提供了一个方便的工具，即 BizTalk 程序集查看器。</span><span class="sxs-lookup"><span data-stu-id="0617d-104">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] provides a convenient tool for this purpose - BizTalk Assembly Viewer.</span></span>  
  
 <span data-ttu-id="0617d-105">BizTalk 程序集查看器是一个 Windows 外壳程序扩展，可用于检查已部署的 BizTalk 程序集和程序集类型。</span><span class="sxs-lookup"><span data-stu-id="0617d-105">The BizTalk Assembly Viewer is a Windows shell extension for examining deployed BizTalk assemblies and assembly types.</span></span> <span data-ttu-id="0617d-106">使用 BizTalk 程序集查看器可以：</span><span class="sxs-lookup"><span data-stu-id="0617d-106">BizTalk Assembly Viewer enables you to:</span></span>  
  
-   <span data-ttu-id="0617d-107">查看安装在本地计算机上的全局程序集缓存 (GAC) 中的所有 BizTalk Server 程序集。</span><span class="sxs-lookup"><span data-stu-id="0617d-107">View a list of all BizTalk Server assemblies installed in the global assembly cache (GAC) on your local computer.</span></span>  
  
-   <span data-ttu-id="0617d-108">查看 BizTalk Server 程序集中的类型。</span><span class="sxs-lookup"><span data-stu-id="0617d-108">View the types within a BizTalk Server assembly.</span></span>  
  
-   <span data-ttu-id="0617d-109">查看 BizTalk Server 程序集的属性，如名称、版本、区域性、代码位置和公钥标记。</span><span class="sxs-lookup"><span data-stu-id="0617d-109">View attributes of a BizTalk Server assembly, such as name, version, culture, code base, and public key token.</span></span>  
  
-   <span data-ttu-id="0617d-110">查看 BizTalk Server 程序集的引用的程序集。</span><span class="sxs-lookup"><span data-stu-id="0617d-110">View referenced assemblies for a BizTalk Server assembly.</span></span>  
  
-   <span data-ttu-id="0617d-111">在 GAC 中添加程序集。</span><span class="sxs-lookup"><span data-stu-id="0617d-111">Add assemblies in the GAC.</span></span>  
  
-   <span data-ttu-id="0617d-112">从 GAC 中删除程序集。</span><span class="sxs-lookup"><span data-stu-id="0617d-112">Remove assemblies from the GAC.</span></span>  
  
-   <span data-ttu-id="0617d-113">查看各种类型（包括架构、映射、业务流程和管道）的 XML 代码。</span><span class="sxs-lookup"><span data-stu-id="0617d-113">View the XML code for various types including schemas, maps, orchestrations, and pipelines.</span></span>  
  
-   <span data-ttu-id="0617d-114">在给定服务器上已部署的全部 BizTalk Server 程序集中搜索特定类型的程序集。</span><span class="sxs-lookup"><span data-stu-id="0617d-114">Search for particular types across all BizTalk Server assemblies deployed on a given server.</span></span>  
  
-   <span data-ttu-id="0617d-115">跨 BizTalk Server 程序集搜索类型依存关系。</span><span class="sxs-lookup"><span data-stu-id="0617d-115">Search type dependencies across BizTalk Server assemblies.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0617d-116">本节内容</span><span class="sxs-lookup"><span data-stu-id="0617d-116">In This Section</span></span>  
  
-   [<span data-ttu-id="0617d-117">如何注册和删除 BizTalk 程序集查看器</span><span class="sxs-lookup"><span data-stu-id="0617d-117">How to Register and Remove the BizTalk Assembly Viewer</span></span>](../core/how-to-register-and-remove-the-biztalk-assembly-viewer.md)  
  
-   [<span data-ttu-id="0617d-118">如何查看本地服务器上的程序集和类型</span><span class="sxs-lookup"><span data-stu-id="0617d-118">How to View Assemblies and Types on the Local Server</span></span>](../core/how-to-view-assemblies-and-types-on-the-local-server.md)