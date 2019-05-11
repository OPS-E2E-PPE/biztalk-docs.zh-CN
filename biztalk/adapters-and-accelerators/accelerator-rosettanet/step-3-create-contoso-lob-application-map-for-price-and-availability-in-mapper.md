---
title: 步骤 3：创建 Contoso LOB 应用程序的价格与可用性项目使用 BizTalk 映射器将映射 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private process tutorial, creating LOB maps
ms.assetid: a947e0ac-f0cb-4be9-85a8-09daf3675b1a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d7a1289bc11517e97bac706803ad0c78dbc2d5c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281150"
---
# <a name="step-3-creating-the-contoso-lob-application-maps-for-the-price-and-availability-project-using-biztalk-mapper"></a><span data-ttu-id="9a994-102">步骤 3：为价格与可用性项目使用 BizTalk 映射器中创建的 Contoso LOB 应用程序映射</span><span class="sxs-lookup"><span data-stu-id="9a994-102">Step 3: Creating the Contoso LOB Application Maps for the Price and Availability Project Using BizTalk Mapper</span></span>
<span data-ttu-id="9a994-103">在此步骤中，将创建两个定义两个贸易合作伙伴之间成功交换消息所需的转换的映射。</span><span class="sxs-lookup"><span data-stu-id="9a994-103">In this step, you create two maps that define the transformation required to successfully exchange messages between the two trading partners.</span></span> <span data-ttu-id="9a994-104">对于此方案，Contoso ERP 系统已进行了标准化的价格与可用性请求的消息格式。</span><span class="sxs-lookup"><span data-stu-id="9a994-104">For this scenario, the Contoso ERP system has already standardized on a message format for a Price and Availability request.</span></span> <span data-ttu-id="9a994-105">两个映射将来自贸易合作伙伴 （Fabrikam) 的请求和响应消息与这些内部定义的 Contoso 消息，分别映射。</span><span class="sxs-lookup"><span data-stu-id="9a994-105">The two maps will map the request and response messages from the trading partner, Fabrikam, to and from those internally defined Contoso messages, respectively.</span></span>  
  
### <a name="to-add-a-reference-for-the-3a2-priceandavailability-request-schema"></a><span data-ttu-id="9a994-106">若要添加为 3A2 PriceAndAvailability 请求架构的引用</span><span class="sxs-lookup"><span data-stu-id="9a994-106">To add a reference for the 3A2 PriceAndAvailability Request schema</span></span>  
  
1.  <span data-ttu-id="9a994-107">在解决方案资源管理器，右键单击 ContosoPriceAndAvailability 项目中，然后依次**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="9a994-107">In Solution Explorer, right-click the ContosoPriceAndAvailability project, and then click **Add Reference**.</span></span>  
  
2.  <span data-ttu-id="9a994-108">在添加引用对话框中，单击**浏览**。</span><span class="sxs-lookup"><span data-stu-id="9a994-108">In the Add Reference dialog box, click **Browse**.</span></span>  
  
3.  <span data-ttu-id="9a994-109">转到的文件夹*\<驱动器\>*: \Program Files\Microsoft BizTalk\<版本\>Accelerator for RosettaNet\Bin，然后选择**Microsoft.Solutions.BTARN.Schemas.RNPIPs.dll**程序集。</span><span class="sxs-lookup"><span data-stu-id="9a994-109">Move to the folder *\<drive\>*:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\Bin, and then select the **Microsoft.Solutions.BTARN.Schemas.RNPIPs.dll** assembly.</span></span>  
  
4.  <span data-ttu-id="9a994-110">单击**外**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="9a994-110">Click **Add**, and then click **OK**.</span></span>  
  
### <a name="to-create-the-3a2-priceandavailability-request-to-contoso-priceandavailability-request-map"></a><span data-ttu-id="9a994-111">若要创建 3A2 PriceAndAvailability 请求到 Contoso PriceAndAvailability 请求的映射</span><span class="sxs-lookup"><span data-stu-id="9a994-111">To create the 3A2 PriceAndAvailability request to Contoso PriceAndAvailability request map</span></span>  
  
1.  <span data-ttu-id="9a994-112">在解决方案资源管理器中右键单击 ContosoPriceAndAvailability 项目，指向**外**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="9a994-112">In Solution Explorer, right-click the ContosoPriceAndAvailability project, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="9a994-113">在添加新项-ContosoPriceAndAvailability 对话框中，选择**地图文件**在类别窗格中，然后选择**地图**中**模板**窗格。</span><span class="sxs-lookup"><span data-stu-id="9a994-113">In the Add New Item - ContosoPriceAndAvailability dialog box, select **Map Files** in the Categories pane, and then select **Map** in the **Templates** pane.</span></span> <span data-ttu-id="9a994-114">在中**名称**框中，键入**PIP3A2RequestToContosoPriceRequest**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="9a994-114">In the **Name** box, type **PIP3A2RequestToContosoPriceRequest**, and then click **Add**.</span></span>  
  
### <a name="to-associate-the-schemas-for-the-pip3a2requesttocontosopricerequest-map"></a><span data-ttu-id="9a994-115">要关联为 PIP3A2RequestToContosoPriceRequest 映射架构</span><span class="sxs-lookup"><span data-stu-id="9a994-115">To associate the schemas for the PIP3A2RequestToContosoPriceRequest map</span></span>  
  
1.  <span data-ttu-id="9a994-116">在 BizTalk 映射器 (显示 pip3a2requesttocontosopricerequest.btm)，在源架构窗格中，单击**打开源架构**。</span><span class="sxs-lookup"><span data-stu-id="9a994-116">In BizTalk Mapper (with PIP3A2RequestToContosoPriceRequest.btm displayed), in the Source Schema pane, click **Open Source Schema**.</span></span>  
  
2.  <span data-ttu-id="9a994-117">在 BizTalk 类型选取器对话框中，展开**ContosoPriceAndAvailability**，展开**引用**，展开**Microsoft.Solutions.BTARN.Schemas.RNPIPs**，，然后展开**架构。**</span><span class="sxs-lookup"><span data-stu-id="9a994-117">In the BizTalk Type Picker dialog box, expand **ContosoPriceAndAvailability**, expand **References**, expand **Microsoft.Solutions.BTARN.Schemas.RNPIPs**, and then expand **Schemas.**</span></span>  
  
3.  <span data-ttu-id="9a994-118">选择**Microsoft.Solutions.BTARN.Schemas.RNPIPs。**</span><span class="sxs-lookup"><span data-stu-id="9a994-118">Select **Microsoft.Solutions.BTARN.Schemas.RNPIPs.**</span></span>  
  
     <span data-ttu-id="9a994-119">**_3A2PriceAndAvailabilityQueryMessageGuideline_v1_3**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="9a994-119">**_3A2PriceAndAvailabilityQueryMessageGuideline_v1_3**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="9a994-120">在目标架构窗格中，单击**打开目标架构**。</span><span class="sxs-lookup"><span data-stu-id="9a994-120">In the Destination Schema pane, click **Open Destination Schema**.</span></span>  
  
5.  <span data-ttu-id="9a994-121">在 BizTalk 类型选取器对话框中，展开**ContosoPriceAndAvailability**，然后展开**架构**。</span><span class="sxs-lookup"><span data-stu-id="9a994-121">In the BizTalk Type Picker dialog box, expand **ContosoPriceAndAvailability**, and then expand **Schemas**.</span></span>  
  
6.  <span data-ttu-id="9a994-122">选择**ContosoPriceAndAvailability.ContosoPriceSchema**架构中，并单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="9a994-122">Select the **ContosoPriceAndAvailability.ContosoPriceSchema** schema, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="9a994-123">在目标架构对话框的根节点中，选择**rootPriceRequest**架构中，并单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="9a994-123">In the Root Node for Target Schema dialog box, select the **rootPriceRequest** schema, and then click **OK**.</span></span>  
  
### <a name="to-link-schema-fields-in-the-pip3a2requesttocontosopricerequest-map"></a><span data-ttu-id="9a994-124">若要 PIP3A2RequestToContosoPriceRequest 映射中链接架构字段</span><span class="sxs-lookup"><span data-stu-id="9a994-124">To link schema fields in the PIP3A2RequestToContosoPriceRequest map</span></span>  
  
1.  <span data-ttu-id="9a994-125">在目标架构窗格中，右键单击**\<架构\>** 节点，，然后单击**展开树节点**。</span><span class="sxs-lookup"><span data-stu-id="9a994-125">In the Destination Schema pane, right-click the **\<Schema\>** node, and then click **Expand Tree Node**.</span></span>  
  
2.  <span data-ttu-id="9a994-126">在源架构窗格中，右键单击**\<架构\>** 节点，，然后单击**展开树节点**。</span><span class="sxs-lookup"><span data-stu-id="9a994-126">In the Source Schema pane, right-click the **\<Schema\>** node, and then click **Expand Tree Node**.</span></span>  
  
3.  <span data-ttu-id="9a994-127">拖动**GlobalProductIdentifier**字段**ProductID**字段在目标架构窗格中。</span><span class="sxs-lookup"><span data-stu-id="9a994-127">Drag the **GlobalProductIdentifier** field to the **ProductID** field in the Destination Schema pane.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9a994-128">您可以找到**GlobalProductIdentifier**字段中的节点 Pip3A2PriceAndAvailabilityQuery 它 /</span><span class="sxs-lookup"><span data-stu-id="9a994-128">You can find the **GlobalProductIdentifier** field in the node Pip3A2PriceAndAvailabilityQuery/ProductPriceAndAvailabilityQuery/</span></span>  
    >   
    >  <span data-ttu-id="9a994-129">ProductPriceAndAvailability/ProductLineItem/productUnit/</span><span class="sxs-lookup"><span data-stu-id="9a994-129">ProductPriceAndAvailability/ProductLineItem/productUnit/</span></span>  
    >   
    >  <span data-ttu-id="9a994-130">ProductPackageDescription/ProductIdentification.</span><span class="sxs-lookup"><span data-stu-id="9a994-130">ProductPackageDescription/ProductIdentification.</span></span>  
  
4.  <span data-ttu-id="9a994-131">上**文件**菜单上，单击**全部保存**以保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="9a994-131">On the **File** menu, click **Save All** to save your changes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a994-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="9a994-132">See Also</span></span>  
 [<span data-ttu-id="9a994-133">创建和配置 Contoso 的 BizTalk 端口</span><span class="sxs-lookup"><span data-stu-id="9a994-133">Creating and Configuring BizTalk Ports for Contoso</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-and-configuring-biztalk-ports-for-contoso.md)