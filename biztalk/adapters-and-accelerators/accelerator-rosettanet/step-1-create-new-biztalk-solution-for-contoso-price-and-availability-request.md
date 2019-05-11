---
title: 第 1 步：为 Contoso 价格与可用性请求创建新的 BizTalk 解决方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private process tutorial, creating solutions
ms.assetid: e323ce26-2031-4293-95bd-a3bf02e535a5
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ad2b35b6b687c820f872bdb63087cca07ead5a4c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281677"
---
# <a name="step-1-creating-a-new-biztalk-solution-for-the-contoso-price-and-availability-request"></a><span data-ttu-id="8fd33-102">第 1 步：为 Contoso 价格与可用性请求创建新的 BizTalk 解决方案</span><span class="sxs-lookup"><span data-stu-id="8fd33-102">Step 1: Creating a New BizTalk Solution for the Contoso Price and Availability Request</span></span>
<span data-ttu-id="8fd33-103">在此步骤中，创建一个 Microsoft[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]将为 Contoso 价格与可用性请求项目的解决方案。</span><span class="sxs-lookup"><span data-stu-id="8fd33-103">In this step, you create a Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] solution for the Contoso Price and Availability Request project.</span></span> <span data-ttu-id="8fd33-104">此项目将包含的架构和映射的请求和响应的 3A2 价格与可用性消息。</span><span class="sxs-lookup"><span data-stu-id="8fd33-104">This project will contain the schemas and maps for the requests and responses for the 3A2 Price and Availability messages.</span></span>  
  
### <a name="to-create-a-blank-solution"></a><span data-ttu-id="8fd33-105">若要创建空白解决方案</span><span class="sxs-lookup"><span data-stu-id="8fd33-105">To create a blank solution</span></span>  
  
1.  <span data-ttu-id="8fd33-106">启动**Microsoft Visual Studio 2012**。</span><span class="sxs-lookup"><span data-stu-id="8fd33-106">Start **Microsoft Visual Studio 2012**.</span></span>  
  
2.  <span data-ttu-id="8fd33-107">在 **“文件”** 菜单上，指向 **“新建”**，再单击 **“项目”**。</span><span class="sxs-lookup"><span data-stu-id="8fd33-107">On the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="8fd33-108">在新建项目对话框中，在**项目类型**部分中，展开**其他项目类型**，选择**Visual Studio 解决方案**，然后在**模板**部分中，选择**空白解决方案**。</span><span class="sxs-lookup"><span data-stu-id="8fd33-108">In the New Project dialog box, in the **Project Types** section, expand **Other Project Types**, select **Visual Studio Solutions**, and then in the **Templates** section, select **Blank Solution**.</span></span>  
  
4.  <span data-ttu-id="8fd33-109">在中**名称**框中，键入**Contoso**作为解决方案的名称，然后单击**确定**以打开新的解决方案。</span><span class="sxs-lookup"><span data-stu-id="8fd33-109">In the **Name** box, type **Contoso** as the solution name, and then click **OK** to open the new solution.</span></span>  
  
### <a name="to-create-the-price-and-availability-project"></a><span data-ttu-id="8fd33-110">若要创建价格与可用性项目</span><span class="sxs-lookup"><span data-stu-id="8fd33-110">To create the Price and Availability project</span></span>  
  
1.  <span data-ttu-id="8fd33-111">在 Visual Studio 中，在**文件**菜单，依次指向**新建**，然后单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="8fd33-111">In Visual Studio, on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="8fd33-112">在新建项目对话框中，在**项目类型**部分中，选择**BizTalk 项目**，然后在**模板**部分中，选择**空 BizTalk服务器项目**。</span><span class="sxs-lookup"><span data-stu-id="8fd33-112">In the New Project dialog box, in the **Project Types** section, select **BizTalk Projects**, and then in the **Templates** section, select **Empty BizTalk Server Project**.</span></span>  
  
3.  <span data-ttu-id="8fd33-113">在中**名称**框中，键入**ContosoPriceAndAvailability**作为项目名称。</span><span class="sxs-lookup"><span data-stu-id="8fd33-113">In the **Name** box, type **ContosoPriceAndAvailability** as the project name.</span></span> <span data-ttu-id="8fd33-114">有关**解决方案**，选择**将添加到解决方案**。</span><span class="sxs-lookup"><span data-stu-id="8fd33-114">For **Solution**, select **Add to Solution**.</span></span> <span data-ttu-id="8fd33-115">单击**确定**打开新项目。</span><span class="sxs-lookup"><span data-stu-id="8fd33-115">Click **OK** to open the new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fd33-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="8fd33-116">See Also</span></span>  
 [<span data-ttu-id="8fd33-117">步骤 2：使用 BizTalk 编辑器创建价格与可用性项目的 Contoso LOB 应用程序架构</span><span class="sxs-lookup"><span data-stu-id="8fd33-117">Step 2: Creating the Contoso LOB Application Schemas for the Price and Availability Project Using BizTalk Editor</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-2-create-contoso-lob-application-schema-for-price-and-availability.md)