---
title: 如何使用密码筛选器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eb429f8b-c301-45a3-8a4f-bbe6f2c566a3
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 22b7939c7a6e00404c9c1b4db586cc9723504aa6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383357"
---
# <a name="how-to-use-password-filters"></a><span data-ttu-id="47c9c-102">如何使用密码筛选器</span><span class="sxs-lookup"><span data-stu-id="47c9c-102">How to Use Password Filters</span></span>
<span data-ttu-id="47c9c-103">ENTSSO 密码同步功能同步 Microsoft Windows Active Directory 和非 Windows 系统之间的密码。</span><span class="sxs-lookup"><span data-stu-id="47c9c-103">The ENTSSO Password Synchronization feature synchronizes passwords between Microsoft Windows Active Directory and non-Windows systems.</span></span> <span data-ttu-id="47c9c-104">但是，许多外部系统具有不同于在 Active Directory 中密码策略要求。</span><span class="sxs-lookup"><span data-stu-id="47c9c-104">However, many external systems have password policy requirements which differ from those in Active Directory.</span></span> <span data-ttu-id="47c9c-105">(例如，IBM 系统可能要求密码为大写并且时间限制为 8 个字符。)这强制 ENTSSO 使用"最小公分"两个系统，限制密码安全性之间。</span><span class="sxs-lookup"><span data-stu-id="47c9c-105">(For example, an IBM system may require a password to be upper case and limited to 8 characters.) This forces ENTSSO to use the “lowest common denominator” between the two systems, limiting password security.</span></span>  
  
 <span data-ttu-id="47c9c-106">ENTSSO 密码筛选器功能来解决此限制。</span><span class="sxs-lookup"><span data-stu-id="47c9c-106">The ENTSSO Password Filter feature addresses this limitation.</span></span> <span data-ttu-id="47c9c-107">密码筛选器是只是密码同步适配器定义的其他属性。</span><span class="sxs-lookup"><span data-stu-id="47c9c-107">A Password Filter is merely a Password Sync Adapter with additional properties defined.</span></span> <span data-ttu-id="47c9c-108">这些额外属性 （如最大或最小长度、 区分和字符限制） 用于筛选密码，以便它们满足外部系统的条件。</span><span class="sxs-lookup"><span data-stu-id="47c9c-108">These additional properties (such as maximum or minimum length, case, and character restrictions) serve to filter the passwords so that they meet the criteria of the external system.</span></span>  
  
 <span data-ttu-id="47c9c-109">请注意，当您创建密码筛选器，指定的管理员组自动用作 SSO Administrators 帐户。</span><span class="sxs-lookup"><span data-stu-id="47c9c-109">Note that when you create a Password Filter, the Administrator group specified is automatically used as the SSO Administrators account.</span></span> <span data-ttu-id="47c9c-110">如果更改 SSO 管理员组，您需要确保密码筛选器也会更新为新的 SSO 管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="47c9c-110">If you change the SSO Administrator group, you will need to make sure the Password Filter is also updated with the new SSO Administrators account.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="47c9c-111">与 ENTSSO 系统中的所有元素，如密码筛选器包含高度敏感的信息，并应被公开到人们可能的最小数目。</span><span class="sxs-lookup"><span data-stu-id="47c9c-111">As with all elements of the ENTSSO system, Password Filters contain highly sensitive information and should be exposed to the minimum number of people possible.</span></span>  
  
### <a name="to-create-a-password-filter"></a><span data-ttu-id="47c9c-112">若要创建密码筛选器</span><span class="sxs-lookup"><span data-stu-id="47c9c-112">To Create a Password Filter</span></span>  
  
1.  <span data-ttu-id="47c9c-113">在中**SSO 管理控制台**，右键单击**密码管理**节点，，然后单击**创建筛选器**。</span><span class="sxs-lookup"><span data-stu-id="47c9c-113">In the **SSO Management Console**, right-click the **Password Management** node, and then click **Create Filter**.</span></span>  
  
     <span data-ttu-id="47c9c-114">**密码筛选器向导**出现。</span><span class="sxs-lookup"><span data-stu-id="47c9c-114">The **Password Filter Wizard** appears.</span></span>  
  
2.  <span data-ttu-id="47c9c-115">按照向导创建密码筛选器的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="47c9c-115">Follow the directions on the Wizard to create the Password Filter.</span></span>  
  
### <a name="to-assign-an-affiliate-application-to-a-password-filter"></a><span data-ttu-id="47c9c-116">若要将分配到密码筛选器的关联应用程序</span><span class="sxs-lookup"><span data-stu-id="47c9c-116">To Assign an Affiliate Application to a Password Filter</span></span>  
  
1.  <span data-ttu-id="47c9c-117">右键单击相应的筛选器，然后依次**分配**...</span><span class="sxs-lookup"><span data-stu-id="47c9c-117">Right-click the appropriate filter, and then click **Assign**….</span></span>  
  
2.  <span data-ttu-id="47c9c-118">选择适当**关联应用程序**。</span><span class="sxs-lookup"><span data-stu-id="47c9c-118">Select the appropriate **Affiliate Application**.</span></span>