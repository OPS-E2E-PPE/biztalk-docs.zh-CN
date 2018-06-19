---
title: 如何使用密码筛选器 |Microsoft 文档
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
ms.openlocfilehash: 3ad35e2c3bec5b2ece69911b8de8c7fd13c9b790
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255933"
---
# <a name="how-to-use-password-filters"></a><span data-ttu-id="f2ddb-102">如何使用密码筛选器</span><span class="sxs-lookup"><span data-stu-id="f2ddb-102">How to Use Password Filters</span></span>
<span data-ttu-id="f2ddb-103">ENTSSO 密码同步功能在 Microsoft Windows Active Directory 和非 Windows 系统之间同步密码。</span><span class="sxs-lookup"><span data-stu-id="f2ddb-103">The ENTSSO Password Synchronization feature synchronizes passwords between Microsoft Windows Active Directory and non-Windows systems.</span></span> <span data-ttu-id="f2ddb-104">但是，许多外部系统具有与 Active Directory 不同的密码策略要求。</span><span class="sxs-lookup"><span data-stu-id="f2ddb-104">However, many external systems have password policy requirements which differ from those in Active Directory.</span></span> <span data-ttu-id="f2ddb-105">（例如，IBM 系统可能要求密码为大写，并且仅限于 8 个字符。）这强制 ENTSSO 在两个系统之间使用“最小公分母”，从而限制了密码的安全性。</span><span class="sxs-lookup"><span data-stu-id="f2ddb-105">(For example, an IBM system may require a password to be upper case and limited to 8 characters.) This forces ENTSSO to use the “lowest common denominator” between the two systems, limiting password security.</span></span>  
  
 <span data-ttu-id="f2ddb-106">ENTSSO 密码筛选器功能解决此限制。</span><span class="sxs-lookup"><span data-stu-id="f2ddb-106">The ENTSSO Password Filter feature addresses this limitation.</span></span> <span data-ttu-id="f2ddb-107">密码筛选器就是定义了额外属性的密码同步适配器。</span><span class="sxs-lookup"><span data-stu-id="f2ddb-107">A Password Filter is merely a Password Sync Adapter with additional properties defined.</span></span> <span data-ttu-id="f2ddb-108">这些额外属性（如最大或最小长度、大小写和字符限制）用于筛选密码，使其满足外部系统的条件。</span><span class="sxs-lookup"><span data-stu-id="f2ddb-108">These additional properties (such as maximum or minimum length, case, and character restrictions) serve to filter the passwords so that they meet the criteria of the external system.</span></span>  
  
 <span data-ttu-id="f2ddb-109">请注意，创建密码筛选器时，指定的 Administrators 组将自动用作 SSO Administrators 帐户。</span><span class="sxs-lookup"><span data-stu-id="f2ddb-109">Note that when you create a Password Filter, the Administrator group specified is automatically used as the SSO Administrators account.</span></span> <span data-ttu-id="f2ddb-110">如果更改 SSO Administrators 组，则需要确保已使用新的 SSO Administrators 帐户更新密码筛选器。</span><span class="sxs-lookup"><span data-stu-id="f2ddb-110">If you change the SSO Administrator group, you will need to make sure the Password Filter is also updated with the new SSO Administrators account.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f2ddb-111">与 ENTSSO 系统中的所有元素一样，密码筛选器包含高度敏感的信息，应向尽可能少的用户公开。</span><span class="sxs-lookup"><span data-stu-id="f2ddb-111">As with all elements of the ENTSSO system, Password Filters contain highly sensitive information and should be exposed to the minimum number of people possible.</span></span>  
  
### <a name="to-create-a-password-filter"></a><span data-ttu-id="f2ddb-112">创建密码筛选器</span><span class="sxs-lookup"><span data-stu-id="f2ddb-112">To Create a Password Filter</span></span>  
  
1.  <span data-ttu-id="f2ddb-113">在**SSO 管理控制台**，右键单击**密码管理**节点，，然后单击**创建筛选器**。</span><span class="sxs-lookup"><span data-stu-id="f2ddb-113">In the **SSO Management Console**, right-click the **Password Management** node, and then click **Create Filter**.</span></span>  
  
     <span data-ttu-id="f2ddb-114">**密码筛选器向导**显示。</span><span class="sxs-lookup"><span data-stu-id="f2ddb-114">The **Password Filter Wizard** appears.</span></span>  
  
2.  <span data-ttu-id="f2ddb-115">按照向导中的说明创建密码筛选器。</span><span class="sxs-lookup"><span data-stu-id="f2ddb-115">Follow the directions on the Wizard to create the Password Filter.</span></span>  
  
### <a name="to-assign-an-affiliate-application-to-a-password-filter"></a><span data-ttu-id="f2ddb-116">将关联应用程序分配到密码筛选器</span><span class="sxs-lookup"><span data-stu-id="f2ddb-116">To Assign an Affiliate Application to a Password Filter</span></span>  
  
1.  <span data-ttu-id="f2ddb-117">右键单击相应的筛选器，并依次**分配**...</span><span class="sxs-lookup"><span data-stu-id="f2ddb-117">Right-click the appropriate filter, and then click **Assign**….</span></span>  
  
2.  <span data-ttu-id="f2ddb-118">选择相应**Affiliate 应用程序**。</span><span class="sxs-lookup"><span data-stu-id="f2ddb-118">Select the appropriate **Affiliate Application**.</span></span>