---
title: 如何包括和排除架构 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e9206458-e5d6-48d7-87a6-9471ba60dca7
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8dfa1f610cef6e67f17ca14737c6ca853dd5cd16
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254341"
---
# <a name="how-to-include-and-exclude-schemas"></a><span data-ttu-id="3b698-102">如何包括和排除架构</span><span class="sxs-lookup"><span data-stu-id="3b698-102">How to Include and Exclude Schemas</span></span>
<span data-ttu-id="3b698-103">架构文件可以存在于 BizTalk 项目文件夹中，但并不包括在该项目中。</span><span class="sxs-lookup"><span data-stu-id="3b698-103">A schema file can exist in a BizTalk project folder and not be included in that project.</span></span> <span data-ttu-id="3b698-104">此类架构称为从项目中排除。</span><span class="sxs-lookup"><span data-stu-id="3b698-104">Such a schema is said to be excluded from the project.</span></span> <span data-ttu-id="3b698-105">生成 BizTalk 项目时不会编译排除的架构。</span><span class="sxs-lookup"><span data-stu-id="3b698-105">Excluded schemas are not compiled when you build the BizTalk project.</span></span> <span data-ttu-id="3b698-106">本主题将介绍在 BizTalk 项目中包括已排除的架构以及从 BizTalk 项目中排除架构所需的步骤。</span><span class="sxs-lookup"><span data-stu-id="3b698-106">This topic describes the steps required to include an excluded schema in a BizTalk project, and to exclude a schema from a BizTalk project.</span></span>  
  
### <a name="to-include-a-schema-in-a-biztalk-project"></a><span data-ttu-id="3b698-107">在 BizTalk 项目中包括架构</span><span class="sxs-lookup"><span data-stu-id="3b698-107">To include a schema in a BizTalk project</span></span>  
  
1.  <span data-ttu-id="3b698-108">在解决方案资源管理器中，打开包含要包括在其项目文件夹中的架构的 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="3b698-108">In Solution Explorer, open the BizTalk project that contains the schema to be included in its project folder.</span></span>  
  
2.  <span data-ttu-id="3b698-109">如果所有文件都未已都显示，在**项目**菜单上，单击**显示所有文件**。</span><span class="sxs-lookup"><span data-stu-id="3b698-109">If all files are not already showing, on the **Project** menu, click **Show All Files**.</span></span>  
  
3.  <span data-ttu-id="3b698-110">在解决方案资源管理器，右键单击你想要包括，然后单击排除的架构**包括在项目**。</span><span class="sxs-lookup"><span data-stu-id="3b698-110">In Solution Explorer, right-click the excluded schema that you want to include, and then click **Include In Project**.</span></span>  
  
     <span data-ttu-id="3b698-111">解决方案资源管理器中先前排除的架构的图标从空轮廓变为正常的架构图标。</span><span class="sxs-lookup"><span data-stu-id="3b698-111">The icon for the previously excluded schema in Solution Explorer changes from an empty outline to the normal schema icon.</span></span>  
  
4.  <span data-ttu-id="3b698-112">（可选） 在**项目**菜单上，单击**显示所有文件**若要隐藏的项目文件夹中不包括在项目的所有文件。</span><span class="sxs-lookup"><span data-stu-id="3b698-112">Optionally, on the **Project** menu, click **Show All Files** to hide all files in the project folder that are not included in the project.</span></span>  
  
### <a name="to-exclude-a-schema-from-a-biztalk-project"></a><span data-ttu-id="3b698-113">从 BizTalk 项目中排除架构</span><span class="sxs-lookup"><span data-stu-id="3b698-113">To exclude a schema from a BizTalk project</span></span>  
  
-   <span data-ttu-id="3b698-114">在解决方案资源管理器，右键单击你想要排除，并依次架构**从项目中排除**。</span><span class="sxs-lookup"><span data-stu-id="3b698-114">In Solution Explorer, right-click the schema that you want to exclude, and then click **Exclude From Project**.</span></span>  
  
     <span data-ttu-id="3b698-115">此时该架构将从 BizTalk 项目中排除。</span><span class="sxs-lookup"><span data-stu-id="3b698-115">The schema is now excluded from the BizTalk project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3b698-116">从项目中排除某架构时，该架构不会从文件系统中删除。</span><span class="sxs-lookup"><span data-stu-id="3b698-116">When you exclude a schema from a project, the schema is not removed from the file system.</span></span> <span data-ttu-id="3b698-117">但是，生成项目时不会包括该架构。</span><span class="sxs-lookup"><span data-stu-id="3b698-117">However, the schema is not included when you build the project.</span></span> <span data-ttu-id="3b698-118">你可以选择是否在项目文件夹中要排除的文件，通过切换**显示所有文件**在解决方案资源管理器窗口顶部的工具。</span><span class="sxs-lookup"><span data-stu-id="3b698-118">You can choose whether or not to display excluded files in the project folder by toggling the **Show All Files** tool at the top of the Solution Explorer window.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3b698-119">在将架构文件从项目中删除时，如果也要将架构从文件系统中删除，则需要删除架构。</span><span class="sxs-lookup"><span data-stu-id="3b698-119">If you want to delete the schema from the file system as well as removing the schema file from the project, you need to delete the schema.</span></span> <span data-ttu-id="3b698-120">有关删除架构的详细信息，请参阅[删除架构](../core/how-to-delete-schemas.md)。</span><span class="sxs-lookup"><span data-stu-id="3b698-120">For more information about deleting schemas, see [Deleting Schemas](../core/how-to-delete-schemas.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b698-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3b698-121">See Also</span></span>  
 [<span data-ttu-id="3b698-122">管理架构在项目中</span><span class="sxs-lookup"><span data-stu-id="3b698-122">Managing Schemas Within Projects</span></span>](../core/managing-schemas-within-projects.md)