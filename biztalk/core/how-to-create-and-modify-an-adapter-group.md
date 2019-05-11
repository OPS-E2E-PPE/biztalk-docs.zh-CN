---
title: 如何创建和修改适配器组 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a1eef051-2ed7-4e28-8cb9-0145d6c8ed76
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ff60beb673515421054863799f7445304a5be200
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65339499"
---
# <a name="how-to-create-and-modify-an-adapter-group"></a><span data-ttu-id="20232-102">如何创建和修改适配器组</span><span class="sxs-lookup"><span data-stu-id="20232-102">How to Create and Modify an Adapter Group</span></span>
<span data-ttu-id="20232-103">单一登录 (SSO) 的新功能之一是能够创建和修改适配器组。</span><span class="sxs-lookup"><span data-stu-id="20232-103">One of the new features of Single Sign-On (SSO) is the ability to create and modify adapter groups.</span></span> <span data-ttu-id="20232-104">顾名思义，适配器组是适配器的集合。</span><span class="sxs-lookup"><span data-stu-id="20232-104">As the name implies, an adapter group is a collection of adapters.</span></span> <span data-ttu-id="20232-105">可以使用适配器组来组织为您的适配器的安全设置和其他属性。</span><span class="sxs-lookup"><span data-stu-id="20232-105">You can use adapter groups to organize security settings and other properties for your adapters.</span></span>  
  
### <a name="to-create-and-modify-an-adapter-group"></a><span data-ttu-id="20232-106">若要创建和修改适配器组</span><span class="sxs-lookup"><span data-stu-id="20232-106">To create and modify an adapter group</span></span>  
  
1.  <span data-ttu-id="20232-107">使用 ssops 工具调用创建适配器组。</span><span class="sxs-lookup"><span data-stu-id="20232-107">Create the adapter group by using a call to the ssops tool.</span></span>  
  
     <span data-ttu-id="20232-108">在关联的 XML 文件中，您必须设置为适配器组的组标志。</span><span class="sxs-lookup"><span data-stu-id="20232-108">In the associated XML file, you must set the group flag as an adapter group.</span></span>  
  
2.  <span data-ttu-id="20232-109">使用将一个或多个适配器添加到适配器组`ISSOPSAdmin.AddAdapterToAdapterGroup`。</span><span class="sxs-lookup"><span data-stu-id="20232-109">Add one or more adapters to the adapter group by using `ISSOPSAdmin.AddAdapterToAdapterGroup`.</span></span>  
  
     <span data-ttu-id="20232-110">此时，适配器组已准备好按预期方式工作。</span><span class="sxs-lookup"><span data-stu-id="20232-110">At this point, your adapter group is ready to work as intended.</span></span> <span data-ttu-id="20232-111">如果有必要，您可以查看相关联的适配器的完整列表使用`ISSOPSAdmin.GetAdaptersForAdapterGroup`。</span><span class="sxs-lookup"><span data-stu-id="20232-111">If necessary, you can view the full list of associated adapters by using `ISSOPSAdmin.GetAdaptersForAdapterGroup`.</span></span>  
  
3.  <span data-ttu-id="20232-112">您可以修改适配器组使用的设置`ISSOPSAdmin.SetAdapterProperties`。</span><span class="sxs-lookup"><span data-stu-id="20232-112">You can modify the settings of your adapter group using `ISSOPSAdmin.SetAdapterProperties`.</span></span>  
  
4.  <span data-ttu-id="20232-113">完成后，可以删除该适配器从适配器组使用`ISSOPSAdmin.RemoveAdapterFromAdapterGroup`。</span><span class="sxs-lookup"><span data-stu-id="20232-113">When you are finished, you can remove the adapter from the adapter group using `ISSOPSAdmin.RemoveAdapterFromAdapterGroup`.</span></span>  
  
5.  <span data-ttu-id="20232-114">最后，通过使用删除适配器组`ISSOAdmin.DeleteApplication`。</span><span class="sxs-lookup"><span data-stu-id="20232-114">Finally, you can delete the adapter group by using `ISSOAdmin.DeleteApplication`.</span></span>  
  
     <span data-ttu-id="20232-115">您也可改为使用删除适配器组`-delete`ssops 工具的命令。</span><span class="sxs-lookup"><span data-stu-id="20232-115">You may choose instead to delete the adapter group by using the `-delete` command of the ssops tool.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20232-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="20232-116">See Also</span></span>  
 [<span data-ttu-id="20232-117">同步密码</span><span class="sxs-lookup"><span data-stu-id="20232-117">Synchronizing Passwords</span></span>](../core/synchronizing-passwords.md)