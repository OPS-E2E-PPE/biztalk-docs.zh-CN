---
title: AddResource 命令 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7b09bd8d-5e07-4443-b626-60401a158540
caps.latest.revision: 33
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d5d8831cbac23343186eb4df9959378cb49fe279
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360203"
---
# <a name="addresource-command"></a><span data-ttu-id="2a33a-102">AddResource 命令</span><span class="sxs-lookup"><span data-stu-id="2a33a-102">AddResource Command</span></span>
<span data-ttu-id="2a33a-103">在本部分中的主题提供 AddResource 命令的参数的参考的信息。</span><span class="sxs-lookup"><span data-stu-id="2a33a-103">The topics in this section provide reference information about the parameters of the AddResource command.</span></span> <span data-ttu-id="2a33a-104">使用此命令使用的参数因你想要添加的项目的类型而异。</span><span class="sxs-lookup"><span data-stu-id="2a33a-104">The parameters that you use with this command vary according to the type of artifact that you want to add.</span></span> <span data-ttu-id="2a33a-105">若要获取的项目类型的完整列表，请使用**ListTypes**命令，如中所述[ListTypes 命令](../core/listtypes-command.md)。</span><span class="sxs-lookup"><span data-stu-id="2a33a-105">To obtain complete lists of artifact types, use the **ListTypes** command, as described in [ListTypes Command](../core/listtypes-command.md).</span></span>  
  
 <span data-ttu-id="2a33a-106">若要添加特定项目类型获取帮助，请键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="2a33a-106">To get help for adding a particular artifact type, type the following command:</span></span>  
  
 <span data-ttu-id="2a33a-107">**BTSTask AddResource /Type:**\<*类型名称*\> **/？**</span><span class="sxs-lookup"><span data-stu-id="2a33a-107">**BTSTask AddResource /Type:**\<*type name*\> **/?**</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2a33a-108">如果要添加的项目具有很长的路径名称，包括文件名称，要将项目添加到应用程序的操作可能会失败。</span><span class="sxs-lookup"><span data-stu-id="2a33a-108">If the artifact you are adding has a very long path name, including the file name, the operation to add the artifact to an application may fail.</span></span> <span data-ttu-id="2a33a-109">路径不能超过 260 个字符。</span><span class="sxs-lookup"><span data-stu-id="2a33a-109">A path cannot exceed 260 characters.</span></span>  
>   
>  <span data-ttu-id="2a33a-110">如果添加操作失败，请在操作期间执行的所有操作都回滚，只不过如果添加此命令，并且如果进行了任何条目，条目不会删除从 Windows 注册表，程序集不会删除从全局程序集缓存。</span><span class="sxs-lookup"><span data-stu-id="2a33a-110">If an add operation fails, all actions taken during the operation are rolled back, except that assemblies are not removed from the global assembly cache if they were added by this command, and entries are not removed from the Windows registry if any entries were made.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2a33a-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="2a33a-111">In This Section</span></span>  
  
-   [<span data-ttu-id="2a33a-112">AddResource 命令：BizTalk 程序集</span><span class="sxs-lookup"><span data-stu-id="2a33a-112">AddResource Command: BizTalk Assembly</span></span>](../core/addresource-command-biztalk-assembly.md)  
  
-   [<span data-ttu-id="2a33a-113">AddResource 命令：BizTalk 绑定</span><span class="sxs-lookup"><span data-stu-id="2a33a-113">AddResource Command: BizTalk Binding</span></span>](../core/addresource-command-biztalk-binding.md)  
  
-   [<span data-ttu-id="2a33a-114">AddResource 命令：.NET 程序集</span><span class="sxs-lookup"><span data-stu-id="2a33a-114">AddResource Command: .NET Assembly</span></span>](../core/addresource-command-net-assembly.md)  
  
-   [<span data-ttu-id="2a33a-115">AddResource 命令：BAM 项目</span><span class="sxs-lookup"><span data-stu-id="2a33a-115">AddResource Command: BAM Artifact</span></span>](../core/addresource-command-bam-artifact.md)  
  
-   [<span data-ttu-id="2a33a-116">AddResource 命令：证书</span><span class="sxs-lookup"><span data-stu-id="2a33a-116">AddResource Command: Certificate</span></span>](../core/addresource-command-certificate.md)  
  
-   [<span data-ttu-id="2a33a-117">AddResource 命令：COM 组件</span><span class="sxs-lookup"><span data-stu-id="2a33a-117">AddResource Command: COM Component</span></span>](../core/addresource-command-com-component.md)  
  
-   [<span data-ttu-id="2a33a-118">AddResource 命令：文件</span><span class="sxs-lookup"><span data-stu-id="2a33a-118">AddResource Command: File</span></span>](../core/addresource-command-file.md)  
  
-   [<span data-ttu-id="2a33a-119">AddResource 命令：预处理脚本</span><span class="sxs-lookup"><span data-stu-id="2a33a-119">AddResource Command: Preprocessing Script</span></span>](../core/addresource-command-preprocessing-script.md)  
  
-   [<span data-ttu-id="2a33a-120">AddResource 命令：后续处理脚本</span><span class="sxs-lookup"><span data-stu-id="2a33a-120">AddResource Command: Postprocessing Script</span></span>](../core/addresource-command-postprocessing-script.md)  
  
-   [<span data-ttu-id="2a33a-121">AddResource 命令：策略</span><span class="sxs-lookup"><span data-stu-id="2a33a-121">AddResource Command: Policy</span></span>](../core/addresource-command-policy.md)  
  
-   [<span data-ttu-id="2a33a-122">AddResource 命令：虚拟目录</span><span class="sxs-lookup"><span data-stu-id="2a33a-122">AddResource Command: Virtual Directory</span></span>](../core/addresource-command-virtual-directory.md)