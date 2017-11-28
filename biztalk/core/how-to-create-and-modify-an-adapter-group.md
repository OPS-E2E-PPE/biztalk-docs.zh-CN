---
title: "如何创建和修改适配器组 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a1eef051-2ed7-4e28-8cb9-0145d6c8ed76
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6865de8eb67d9fe1a6ca8d93b7d2e6527ae36364
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-and-modify-an-adapter-group"></a><span data-ttu-id="55591-102">如何创建和修改适配器组</span><span class="sxs-lookup"><span data-stu-id="55591-102">How to Create and Modify an Adapter Group</span></span>
<span data-ttu-id="55591-103">新功能的单一登录 (SSO) 之一是能够创建和修改适配器组。</span><span class="sxs-lookup"><span data-stu-id="55591-103">One of the new features of Single Sign-On (SSO) is the ability to create and modify adapter groups.</span></span> <span data-ttu-id="55591-104">顾名思义，适配器组是适配器的集合。</span><span class="sxs-lookup"><span data-stu-id="55591-104">As the name implies, an adapter group is a collection of adapters.</span></span> <span data-ttu-id="55591-105">可以使用适配器组来组织为你的适配器的安全设置和其他属性。</span><span class="sxs-lookup"><span data-stu-id="55591-105">You can use adapter groups to organize security settings and other properties for your adapters.</span></span>  
  
### <a name="to-create-and-modify-an-adapter-group"></a><span data-ttu-id="55591-106">若要创建和修改适配器组</span><span class="sxs-lookup"><span data-stu-id="55591-106">To create and modify an adapter group</span></span>  
  
1.  <span data-ttu-id="55591-107">通过调用 ssops 工具创建适配器组。</span><span class="sxs-lookup"><span data-stu-id="55591-107">Create the adapter group by using a call to the ssops tool.</span></span>  
  
     <span data-ttu-id="55591-108">在关联的 XML 文件中，你必须将组标志设置为适配器组。</span><span class="sxs-lookup"><span data-stu-id="55591-108">In the associated XML file, you must set the group flag as an adapter group.</span></span>  
  
2.  <span data-ttu-id="55591-109">通过将一个或多个适配器添加到适配器组`ISSOPSAdmin.AddAdapterToAdapterGroup`。</span><span class="sxs-lookup"><span data-stu-id="55591-109">Add one or more adapters to the adapter group by using `ISSOPSAdmin.AddAdapterToAdapterGroup`.</span></span>  
  
     <span data-ttu-id="55591-110">此时，你的适配器组已准备好按预期方式工作。</span><span class="sxs-lookup"><span data-stu-id="55591-110">At this point, your adapter group is ready to work as intended.</span></span> <span data-ttu-id="55591-111">如果有必要，你可以查看关联的适配器的完整列表使用`ISSOPSAdmin.GetAdaptersForAdapterGroup`。</span><span class="sxs-lookup"><span data-stu-id="55591-111">If necessary, you can view the full list of associated adapters by using `ISSOPSAdmin.GetAdaptersForAdapterGroup`.</span></span>  
  
3.  <span data-ttu-id="55591-112">你可以修改适配器组使用的设置`ISSOPSAdmin.SetAdapterProperties`。</span><span class="sxs-lookup"><span data-stu-id="55591-112">You can modify the settings of your adapter group using `ISSOPSAdmin.SetAdapterProperties`.</span></span>  
  
4.  <span data-ttu-id="55591-113">完成后，你可以从适配器组使用删除适配器`ISSOPSAdmin.RemoveAdapterFromAdapterGroup`。</span><span class="sxs-lookup"><span data-stu-id="55591-113">When you are finished, you can remove the adapter from the adapter group using `ISSOPSAdmin.RemoveAdapterFromAdapterGroup`.</span></span>  
  
5.  <span data-ttu-id="55591-114">最后，可以通过使用删除适配器组`ISSOAdmin.DeleteApplication`。</span><span class="sxs-lookup"><span data-stu-id="55591-114">Finally, you can delete the adapter group by using `ISSOAdmin.DeleteApplication`.</span></span>  
  
     <span data-ttu-id="55591-115">你可以选择改为使用删除适配器组`-delete`ssops 工具的命令。</span><span class="sxs-lookup"><span data-stu-id="55591-115">You may choose instead to delete the adapter group by using the `-delete` command of the ssops tool.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55591-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="55591-116">See Also</span></span>  
 [<span data-ttu-id="55591-117">同步密码</span><span class="sxs-lookup"><span data-stu-id="55591-117">Synchronizing Passwords</span></span>](../core/synchronizing-passwords.md)