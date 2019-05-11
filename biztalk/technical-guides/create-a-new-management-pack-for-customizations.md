---
title: 为自定义项创建新的管理包 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4ce1ffa0-57c7-41ce-b459-48c36522889e
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 53ff5ede763b8a8b9b0e4de55231f1b1bd70b946
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65306063"
---
# <a name="create-a-new-management-pack-for-customizations"></a><span data-ttu-id="e2a2d-102">为自定义项创建新的管理包</span><span class="sxs-lookup"><span data-stu-id="e2a2d-102">Create a New Management Pack for Customizations</span></span>
<span data-ttu-id="e2a2d-103">大多数供应商管理包被密封的不能更改任何管理包文件中的原始设置。</span><span class="sxs-lookup"><span data-stu-id="e2a2d-103">Most vendor management packs are sealed so that you cannot change any of the original settings in the management pack file.</span></span> <span data-ttu-id="e2a2d-104">但是，您可以创建自定义，例如替代或新的监视对象，然后将它们保存到不同管理包。</span><span class="sxs-lookup"><span data-stu-id="e2a2d-104">However, you can create customizations, such as overrides or new monitoring objects, and save them to a different management pack.</span></span> <span data-ttu-id="e2a2d-105">默认情况下，Operations Manager 2007 R2/2012年将所有自定义项保存到默认管理包。</span><span class="sxs-lookup"><span data-stu-id="e2a2d-105">By default, Operations Manager 2007 R2/2012 saves all customizations to the Default Management Pack.</span></span> <span data-ttu-id="e2a2d-106">作为最佳做法，应改为创建单独的管理包为你想要自定义每个密封的管理包。</span><span class="sxs-lookup"><span data-stu-id="e2a2d-106">As a best practice, you should instead create a separate management pack for each sealed management pack that you want to customize.</span></span>  
  
 <span data-ttu-id="e2a2d-107">创建新管理包来存储替代具有下列优势：</span><span class="sxs-lookup"><span data-stu-id="e2a2d-107">Creating a new management pack for storing overrides has the following advantages:</span></span>  
  
- <span data-ttu-id="e2a2d-108">简化了将测试和预生产环境中创建的自定义导出到生产环境的过程。</span><span class="sxs-lookup"><span data-stu-id="e2a2d-108">It simplifies the process of exporting customizations that were created in your test and pre-production environments to your production environment.</span></span> <span data-ttu-id="e2a2d-109">例如，而无需导出包含来自多个管理包自定义项的默认管理包，可以导出只包含单个管理包的自定义管理包。</span><span class="sxs-lookup"><span data-stu-id="e2a2d-109">For example, instead of exporting the Default Management Pack that contains customizations from multiple management packs, you can export just the management pack that contains customizations of a single management pack.</span></span>  
  
- <span data-ttu-id="e2a2d-110">而不必首先删除默认管理包，可以删除原始管理包。</span><span class="sxs-lookup"><span data-stu-id="e2a2d-110">You can delete the original management pack without first having to delete the Default Management Pack.</span></span> <span data-ttu-id="e2a2d-111">包含自定义项的管理包依赖于原始管理包。</span><span class="sxs-lookup"><span data-stu-id="e2a2d-111">A management pack that contains customizations depends on the original management pack.</span></span> <span data-ttu-id="e2a2d-112">这种依赖性要求删除包含自定义的管理包后，才能删除原始管理包。</span><span class="sxs-lookup"><span data-stu-id="e2a2d-112">This dependency requires you to delete the management pack with customizations before you can delete the original management pack.</span></span> <span data-ttu-id="e2a2d-113">如果所有自定义保存到默认管理包，必须删除默认管理包，然后才能删除原始管理包。</span><span class="sxs-lookup"><span data-stu-id="e2a2d-113">If all of your customizations are saved to the Default Management Pack, you must delete the Default Management Pack before you can delete an original management pack.</span></span>  
  
- <span data-ttu-id="e2a2d-114">跟踪和更新单个管理包的自定义变得更加简单。</span><span class="sxs-lookup"><span data-stu-id="e2a2d-114">It is easier to track and update customizations to individual management packs.</span></span>  
  
  <span data-ttu-id="e2a2d-115">有关详细信息大约密封和未密封管理包，请参阅[管理包格式](http://go.microsoft.com/fwlink/?LinkID=198193)(http://go.microsoft.com/fwlink/?LinkId=198193)。</span><span class="sxs-lookup"><span data-stu-id="e2a2d-115">For more information about sealed and unsealed management packs, see [Management Pack Formats](http://go.microsoft.com/fwlink/?LinkID=198193) (http://go.microsoft.com/fwlink/?LinkId=198193).</span></span> <span data-ttu-id="e2a2d-116">有关管理包自定义的详细信息，请参阅[自定义管理包](http://go.microsoft.com/fwlink/?LinkID=198194)(http://go.microsoft.com/fwlink/?LinkID=198194)。</span><span class="sxs-lookup"><span data-stu-id="e2a2d-116">For more information about management pack customizations, see [Customizing Management Packs](http://go.microsoft.com/fwlink/?LinkID=198194) (http://go.microsoft.com/fwlink/?LinkID=198194).</span></span>