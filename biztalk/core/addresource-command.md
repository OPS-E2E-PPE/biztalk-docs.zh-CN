---
title: "AddResource 命令 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7b09bd8d-5e07-4443-b626-60401a158540
caps.latest.revision: "33"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 97d2cb07bd0a05ddd1e79f4048bfe30e51e8d866
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="addresource-command"></a><span data-ttu-id="0ea93-102">AddResource 命令</span><span class="sxs-lookup"><span data-stu-id="0ea93-102">AddResource Command</span></span>
<span data-ttu-id="0ea93-103">本部分中主题提供关于 AddResource 命令的参数的参考信息。</span><span class="sxs-lookup"><span data-stu-id="0ea93-103">The topics in this section provide reference information about the parameters of the AddResource command.</span></span> <span data-ttu-id="0ea93-104">使用此命令使用的参数因你想要添加的项目的类型。</span><span class="sxs-lookup"><span data-stu-id="0ea93-104">The parameters that you use with this command vary according to the type of artifact that you want to add.</span></span> <span data-ttu-id="0ea93-105">若要获取的项目类型的完整列表，请使用**默认应用**命令时中, 所述[默认应用命令](../core/listtypes-command.md)。</span><span class="sxs-lookup"><span data-stu-id="0ea93-105">To obtain complete lists of artifact types, use the **ListTypes** command, as described in [ListTypes Command](../core/listtypes-command.md).</span></span>  
  
 <span data-ttu-id="0ea93-106">若要获得添加特定项目类型的帮助，请键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="0ea93-106">To get help for adding a particular artifact type, type the following command:</span></span>  
  
 <span data-ttu-id="0ea93-107">**BTSTask AddResource /Type:**\<*类型名称*> **/？**</span><span class="sxs-lookup"><span data-stu-id="0ea93-107">**BTSTask AddResource /Type:**\<*type name*> **/?**</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0ea93-108">如果要添加的项目具有很长的路径名（包括文件名），则将项目添加到应用程序的操作可能失败。</span><span class="sxs-lookup"><span data-stu-id="0ea93-108">If the artifact you are adding has a very long path name, including the file name, the operation to add the artifact to an application may fail.</span></span> <span data-ttu-id="0ea93-109">路径名不能超过 260 个字符。</span><span class="sxs-lookup"><span data-stu-id="0ea93-109">A path cannot exceed 260 characters.</span></span>  
>   
>  <span data-ttu-id="0ea93-110">如果添加操作失败，除以下两种情况外，添加过程中执行的所有操作均被回滚：此命令添加到全局程序集缓存中的程序集不从全局程序集缓存中删除；在 Windows 注册表中添加的项不从注册表中删除。</span><span class="sxs-lookup"><span data-stu-id="0ea93-110">If an add operation fails, all actions taken during the operation are rolled back, except that assemblies are not removed from the global assembly cache if they were added by this command, and entries are not removed from the Windows registry if any entries were made.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0ea93-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="0ea93-111">In This Section</span></span>  
  
-   [<span data-ttu-id="0ea93-112">AddResource 命令： BizTalk 程序集</span><span class="sxs-lookup"><span data-stu-id="0ea93-112">AddResource Command: BizTalk Assembly</span></span>](../core/addresource-command-biztalk-assembly.md)  
  
-   [<span data-ttu-id="0ea93-113">AddResource 命令： BizTalk 绑定</span><span class="sxs-lookup"><span data-stu-id="0ea93-113">AddResource Command: BizTalk Binding</span></span>](../core/addresource-command-biztalk-binding.md)  
  
-   [<span data-ttu-id="0ea93-114">AddResource 命令：.NET 程序集</span><span class="sxs-lookup"><span data-stu-id="0ea93-114">AddResource Command: .NET Assembly</span></span>](../core/addresource-command-net-assembly.md)  
  
-   [<span data-ttu-id="0ea93-115">AddResource 命令： BAM 项目</span><span class="sxs-lookup"><span data-stu-id="0ea93-115">AddResource Command: BAM Artifact</span></span>](../core/addresource-command-bam-artifact.md)  
  
-   [<span data-ttu-id="0ea93-116">AddResource 命令： 证书</span><span class="sxs-lookup"><span data-stu-id="0ea93-116">AddResource Command: Certificate</span></span>](../core/addresource-command-certificate.md)  
  
-   [<span data-ttu-id="0ea93-117">AddResource 命令： COM 组件</span><span class="sxs-lookup"><span data-stu-id="0ea93-117">AddResource Command: COM Component</span></span>](../core/addresource-command-com-component.md)  
  
-   [<span data-ttu-id="0ea93-118">AddResource 命令： 文件</span><span class="sxs-lookup"><span data-stu-id="0ea93-118">AddResource Command: File</span></span>](../core/addresource-command-file.md)  
  
-   [<span data-ttu-id="0ea93-119">AddResource 命令： 预处理脚本</span><span class="sxs-lookup"><span data-stu-id="0ea93-119">AddResource Command: Preprocessing Script</span></span>](../core/addresource-command-preprocessing-script.md)  
  
-   [<span data-ttu-id="0ea93-120">AddResource 命令： 后处理脚本</span><span class="sxs-lookup"><span data-stu-id="0ea93-120">AddResource Command: Postprocessing Script</span></span>](../core/addresource-command-postprocessing-script.md)  
  
-   [<span data-ttu-id="0ea93-121">AddResource 命令： 策略</span><span class="sxs-lookup"><span data-stu-id="0ea93-121">AddResource Command: Policy</span></span>](../core/addresource-command-policy.md)  
  
-   [<span data-ttu-id="0ea93-122">AddResource 命令： 虚拟目录</span><span class="sxs-lookup"><span data-stu-id="0ea93-122">AddResource Command: Virtual Directory</span></span>](../core/addresource-command-virtual-directory.md)