---
title: 第 1 步：创建 Contoso 本组织 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- double action tutorial, creating home organizations
- creating, home organizations
- home organizations, creating
ms.assetid: 0e7a53b9-ae59-4cd1-88bd-0ada7e65acba
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3893d582a85708190f1f030b06187fcd8f152bd6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281593"
---
# <a name="step-1-creating-the-contoso-home-organization"></a><span data-ttu-id="cf516-102">第 1 步：创建 Contoso 本组织</span><span class="sxs-lookup"><span data-stu-id="cf516-102">Step 1: Creating the Contoso Home Organization</span></span>
<span data-ttu-id="cf516-103">在此步骤中，使用 Microsoft®[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]管理控制台创建 Contoso 本组织。</span><span class="sxs-lookup"><span data-stu-id="cf516-103">In this step, you use the Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] Management Console to create the Contoso home organization.</span></span>  

### <a name="to-start-the-btarn-management-console"></a><span data-ttu-id="cf516-104">若要启动 BTARN 管理控制台</span><span class="sxs-lookup"><span data-stu-id="cf516-104">To start the BTARN Management Console</span></span>  

- <span data-ttu-id="cf516-105">在 Contoso 计算机上，单击**启动**，依次指向**所有程序**，指向**Microsoft BizTalk\<版本\>Accelerator for RosettaNet**，然后单击**[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="cf516-105">On the Contoso computer, click **Start**, point to **All Programs**, point to **Microsoft  BizTalk \<version\> Accelerator for RosettaNet** and then click **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console.</span></span>  

### <a name="to-create-the-home-organization"></a><span data-ttu-id="cf516-106">若要创建本组织</span><span class="sxs-lookup"><span data-stu-id="cf516-106">To create the home organization</span></span>  

1. <span data-ttu-id="cf516-107">在中[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]管理控制台中，展开[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]，右键单击**本组织**，指向**新建**，然后单击**本组织**。</span><span class="sxs-lookup"><span data-stu-id="cf516-107">In the [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] Management Console, expand [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], right-click **Home Organizations**, point to **New**, and then click **Home Organization**.</span></span>  

2. <span data-ttu-id="cf516-108">在新本组织属性对话框中，在**常规**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="cf516-108">In the New Home Organization Properties dialog box, on the **General** tab, do the following:</span></span>  


   |               <span data-ttu-id="cf516-109">使用此选项</span><span class="sxs-lookup"><span data-stu-id="cf516-109">Use this</span></span>               |                                                                              <span data-ttu-id="cf516-110">执行的操作</span><span class="sxs-lookup"><span data-stu-id="cf516-110">To do this</span></span>                                                                               |
   |--------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |               <span data-ttu-id="cf516-111">**名称**</span><span class="sxs-lookup"><span data-stu-id="cf516-111">**Name**</span></span>               |                                                                           <span data-ttu-id="cf516-112">类型**CONTOSO**。</span><span class="sxs-lookup"><span data-stu-id="cf516-112">Type **CONTOSO**.</span></span>                                                                           |
   |               <span data-ttu-id="cf516-113">**GBI**</span><span class="sxs-lookup"><span data-stu-id="cf516-113">**GBI**</span></span>                | <span data-ttu-id="cf516-114">类型**123456789**。</span><span class="sxs-lookup"><span data-stu-id="cf516-114">Type **123456789**.</span></span> <span data-ttu-id="cf516-115">**注意：** 如果已在同一计算机上运行 Loopback 教程，将需要输入除"123456789"不同的 GBI 值。</span><span class="sxs-lookup"><span data-stu-id="cf516-115">**Note:**  If you have run the Loopback tutorial on the same computer, you will have to enter a value for GBI that is different than "123456789".</span></span> |
   | <span data-ttu-id="cf516-116">**本组织分类**</span><span class="sxs-lookup"><span data-stu-id="cf516-116">**Home Organization Classification**</span></span> |                                                           <span data-ttu-id="cf516-117">选择**制造商**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="cf516-117">Select **Manufacturer** from the drop-down list.</span></span>                                                            |


3. <span data-ttu-id="cf516-118">单击**联系人属性**选项卡，然后再执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="cf516-118">Click the **Contact Properties** tab, and then do the following:</span></span>  


   |       <span data-ttu-id="cf516-119">使用此选项</span><span class="sxs-lookup"><span data-stu-id="cf516-119">Use this</span></span>        |               <span data-ttu-id="cf516-120">执行的操作</span><span class="sxs-lookup"><span data-stu-id="cf516-120">To do this</span></span>                |
   |-----------------------|-----------------------------------------|
   |   <span data-ttu-id="cf516-121">**联系人姓名**</span><span class="sxs-lookup"><span data-stu-id="cf516-121">**Contact Name**</span></span>    |           <span data-ttu-id="cf516-122">类型**John Doe**。</span><span class="sxs-lookup"><span data-stu-id="cf516-122">Type **John Doe**.</span></span>            |
   |  <span data-ttu-id="cf516-123">**E-mail Address**</span><span class="sxs-lookup"><span data-stu-id="cf516-123">**E-mail Address**</span></span>   | <span data-ttu-id="cf516-124">类型<strong>jdoe@contoso.com</strong>。</span><span class="sxs-lookup"><span data-stu-id="cf516-124">Type <strong>jdoe@contoso.com</strong>.</span></span> |
   | <span data-ttu-id="cf516-125">**电话号码**</span><span class="sxs-lookup"><span data-stu-id="cf516-125">**Telephone Number**</span></span>  |         <span data-ttu-id="cf516-126">类型**555-555-5555**。</span><span class="sxs-lookup"><span data-stu-id="cf516-126">Type **555-555-5555**.</span></span>          |
   |    <span data-ttu-id="cf516-127">**传真号码**</span><span class="sxs-lookup"><span data-stu-id="cf516-127">**Fax Number**</span></span>     |         <span data-ttu-id="cf516-128">类型**555-555-5555**。</span><span class="sxs-lookup"><span data-stu-id="cf516-128">Type **555-555-5555**.</span></span>          |
   | <span data-ttu-id="cf516-129">**供应链代码**</span><span class="sxs-lookup"><span data-stu-id="cf516-129">**Supply Chain Code**</span></span> |     <span data-ttu-id="cf516-130">类型**电子元件**。</span><span class="sxs-lookup"><span data-stu-id="cf516-130">Type **Electronic Components**.</span></span>     |


4. <span data-ttu-id="cf516-131">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="cf516-131">Click **OK**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="cf516-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="cf516-132">See Also</span></span>  
 [<span data-ttu-id="cf516-133">步骤 2：创建 Fabrikam 合作伙伴组织</span><span class="sxs-lookup"><span data-stu-id="cf516-133">Step 2: Creating the Fabrikam Partner Organization</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-2-creating-the-fabrikam-partner-organization.md)