---
title: 步骤 1： 创建 Contoso 本组织 |Microsoft Docs
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
ms.openlocfilehash: 303048a06ce1acccac07d10bbe1ac53c32a08122
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000118"
---
# <a name="step-1-creating-the-contoso-home-organization"></a><span data-ttu-id="4fc8c-102">步骤 1： 创建 Contoso 本组织</span><span class="sxs-lookup"><span data-stu-id="4fc8c-102">Step 1: Creating the Contoso Home Organization</span></span>
<span data-ttu-id="4fc8c-103">在此步骤中，使用 Microsoft®[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]管理控制台创建 Contoso 本组织。</span><span class="sxs-lookup"><span data-stu-id="4fc8c-103">In this step, you use the Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] Management Console to create the Contoso home organization.</span></span>  

### <a name="to-start-the-btarn-management-console"></a><span data-ttu-id="4fc8c-104">启动 BTARN 管理控制台</span><span class="sxs-lookup"><span data-stu-id="4fc8c-104">To start the BTARN Management Console</span></span>  

- <span data-ttu-id="4fc8c-105">在 Contoso 计算机上，单击**启动**，依次指向**所有程序**，指向**Microsoft BizTalk\<版本\>Accelerator for RosettaNet**，然后单击**[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="4fc8c-105">On the Contoso computer, click **Start**, point to **All Programs**, point to **Microsoft  BizTalk \<version\> Accelerator for RosettaNet** and then click **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console.</span></span>  

### <a name="to-create-the-home-organization"></a><span data-ttu-id="4fc8c-106">创建本组织</span><span class="sxs-lookup"><span data-stu-id="4fc8c-106">To create the home organization</span></span>  

1. <span data-ttu-id="4fc8c-107">在中[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]管理控制台中，展开[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]，右键单击**本组织**，指向**新建**，然后单击**本组织**。</span><span class="sxs-lookup"><span data-stu-id="4fc8c-107">In the [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] Management Console, expand [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], right-click **Home Organizations**, point to **New**, and then click **Home Organization**.</span></span>  

2. <span data-ttu-id="4fc8c-108">在新本组织属性对话框中，在**常规**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="4fc8c-108">In the New Home Organization Properties dialog box, on the **General** tab, do the following:</span></span>  


   |               <span data-ttu-id="4fc8c-109">使用此选项</span><span class="sxs-lookup"><span data-stu-id="4fc8c-109">Use this</span></span>               |                                                                              <span data-ttu-id="4fc8c-110">执行的操作</span><span class="sxs-lookup"><span data-stu-id="4fc8c-110">To do this</span></span>                                                                               |
   |--------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |               <span data-ttu-id="4fc8c-111">**名称**</span><span class="sxs-lookup"><span data-stu-id="4fc8c-111">**Name**</span></span>               |                                                                           <span data-ttu-id="4fc8c-112">类型**CONTOSO**。</span><span class="sxs-lookup"><span data-stu-id="4fc8c-112">Type **CONTOSO**.</span></span>                                                                           |
   |               <span data-ttu-id="4fc8c-113">**GBI**</span><span class="sxs-lookup"><span data-stu-id="4fc8c-113">**GBI**</span></span>                | <span data-ttu-id="4fc8c-114">类型**123456789**。</span><span class="sxs-lookup"><span data-stu-id="4fc8c-114">Type **123456789**.</span></span> <span data-ttu-id="4fc8c-115">**注意：** 如果同一台计算机上运行 Loopback 教程，必须输入除"123456789"不同的 GBI 值。</span><span class="sxs-lookup"><span data-stu-id="4fc8c-115">**Note:**  If you have run the Loopback tutorial on the same computer, you will have to enter a value for GBI that is different than "123456789".</span></span> |
   | <span data-ttu-id="4fc8c-116">**本组织分类**</span><span class="sxs-lookup"><span data-stu-id="4fc8c-116">**Home Organization Classification**</span></span> |                                                           <span data-ttu-id="4fc8c-117">选择**制造商**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="4fc8c-117">Select **Manufacturer** from the drop-down list.</span></span>                                                            |


3. <span data-ttu-id="4fc8c-118">单击**联系人属性**选项卡，然后再执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="4fc8c-118">Click the **Contact Properties** tab, and then do the following:</span></span>  


   |       <span data-ttu-id="4fc8c-119">使用此选项</span><span class="sxs-lookup"><span data-stu-id="4fc8c-119">Use this</span></span>        |               <span data-ttu-id="4fc8c-120">执行的操作</span><span class="sxs-lookup"><span data-stu-id="4fc8c-120">To do this</span></span>                |
   |-----------------------|-----------------------------------------|
   |   <span data-ttu-id="4fc8c-121">**联系人姓名**</span><span class="sxs-lookup"><span data-stu-id="4fc8c-121">**Contact Name**</span></span>    |           <span data-ttu-id="4fc8c-122">类型**John Doe**。</span><span class="sxs-lookup"><span data-stu-id="4fc8c-122">Type **John Doe**.</span></span>            |
   |  <span data-ttu-id="4fc8c-123">**E-mail Address**</span><span class="sxs-lookup"><span data-stu-id="4fc8c-123">**E-mail Address**</span></span>   | <span data-ttu-id="4fc8c-124">类型<strong>jdoe@contoso.com</strong>。</span><span class="sxs-lookup"><span data-stu-id="4fc8c-124">Type <strong>jdoe@contoso.com</strong>.</span></span> |
   | <span data-ttu-id="4fc8c-125">**电话号码**</span><span class="sxs-lookup"><span data-stu-id="4fc8c-125">**Telephone Number**</span></span>  |         <span data-ttu-id="4fc8c-126">类型**555-555-5555**。</span><span class="sxs-lookup"><span data-stu-id="4fc8c-126">Type **555-555-5555**.</span></span>          |
   |    <span data-ttu-id="4fc8c-127">**传真号码**</span><span class="sxs-lookup"><span data-stu-id="4fc8c-127">**Fax Number**</span></span>     |         <span data-ttu-id="4fc8c-128">类型**555-555-5555**。</span><span class="sxs-lookup"><span data-stu-id="4fc8c-128">Type **555-555-5555**.</span></span>          |
   | <span data-ttu-id="4fc8c-129">**供应链代码**</span><span class="sxs-lookup"><span data-stu-id="4fc8c-129">**Supply Chain Code**</span></span> |     <span data-ttu-id="4fc8c-130">类型**电子元件**。</span><span class="sxs-lookup"><span data-stu-id="4fc8c-130">Type **Electronic Components**.</span></span>     |


4. <span data-ttu-id="4fc8c-131">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="4fc8c-131">Click **OK**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="4fc8c-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="4fc8c-132">See Also</span></span>  
 [<span data-ttu-id="4fc8c-133">步骤 2：创建 Fabrikam 合作伙伴组织</span><span class="sxs-lookup"><span data-stu-id="4fc8c-133">Step 2: Creating the Fabrikam Partner Organization</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-2-creating-the-fabrikam-partner-organization.md)