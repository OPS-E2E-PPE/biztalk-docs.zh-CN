---
title: 步骤 6 （本地）： 创建一个转换，以便将消息从队列到插入架构映射 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 30a55f1e-32cc-409a-a814-084026f51b35
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae0bc6826bda147d4af6ccb47d81eb2513eea640
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981302"
---
# <a name="step-6-on-premises-create-a-transform-to-map-the-message-from-the-queue-to-the-insert-schema"></a><span data-ttu-id="c3d80-102">步骤 6 （本地）： 创建一个转换，以便将消息从队列到插入架构映射</span><span class="sxs-lookup"><span data-stu-id="c3d80-102">Step 6 (On Premises): Create a Transform to Map the Message from the Queue to the Insert Schema</span></span>
<span data-ttu-id="c3d80-103">通过收到的消息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]从服务总线队列都属于**ECommerceSalesOrder.xsd**架构。</span><span class="sxs-lookup"><span data-stu-id="c3d80-103">The message that is received by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] from the Service Bus Queue will be of the **ECommerceSalesOrder.xsd** schema.</span></span> <span data-ttu-id="c3d80-104">但是，若要将消息插入**SalesOrder**表中，消息必须属于**插入**中生成的架构[步骤 5 （本地）： 生成插入消息用于向架构SalesOrder 表](../core/step-5-generate-the-schema-for-inserting-a-message-into-salesorder-table.md)。</span><span class="sxs-lookup"><span data-stu-id="c3d80-104">However, to insert a message into the **SalesOrder** table, the message must be of **Insert** schema that you generated in [Step 5 (On Premises): Generate the Schema for Inserting a Message inito SalesOrder Table](../core/step-5-generate-the-schema-for-inserting-a-message-into-salesorder-table.md).</span></span> <span data-ttu-id="c3d80-105">因此，在本主题中，我们创建一个映射来转换**ECommerceSalesOrder.xsd**到插入操作架构的架构。</span><span class="sxs-lookup"><span data-stu-id="c3d80-105">So, in this topic, we create a map to transform the **ECommerceSalesOrder.xsd** schema into the Insert operation schema.</span></span>  

### <a name="to-create-a-map"></a><span data-ttu-id="c3d80-106">创建映射的步骤</span><span class="sxs-lookup"><span data-stu-id="c3d80-106">To create a map</span></span>  

1. <span data-ttu-id="c3d80-107">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]你已创建，右键单击项目，指向**添加**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="c3d80-107">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] you already created, right-click the project, point to **Add**, and then click **New Item**.</span></span> <span data-ttu-id="c3d80-108">在中**新项**对话框中，选择**映射**，输入作为映射名称`SalesOrder_SQL.btm`，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="c3d80-108">In the **New Item** dialog box, select **Map**, enter the map name as `SalesOrder_SQL.btm`, and then click **Add**.</span></span>  

2. <span data-ttu-id="c3d80-109">在映射中，对于源架构中，选择**ECommerceSalesOrder.xsd**。</span><span class="sxs-lookup"><span data-stu-id="c3d80-109">In the map, for the source schema, select **ECommerceSalesOrder.xsd**.</span></span> <span data-ttu-id="c3d80-110">对于目标架构中，选择**TableOperations.SalesOrder.xsd (Insert)** 架构。</span><span class="sxs-lookup"><span data-stu-id="c3d80-110">For the destination schema, select **TableOperations.SalesOrder.xsd (Insert)** schema.</span></span>  

3. <span data-ttu-id="c3d80-111">直接映射源架构和目标架构中的以下节点：</span><span class="sxs-lookup"><span data-stu-id="c3d80-111">Directly map the following nodes in the source and destination schemas:</span></span>  


   | <span data-ttu-id="c3d80-112">源架构</span><span class="sxs-lookup"><span data-stu-id="c3d80-112">Source Schema</span></span> | <span data-ttu-id="c3d80-113">目标架构</span><span class="sxs-lookup"><span data-stu-id="c3d80-113">Destination Schema</span></span> |
   |---------------|--------------------|
   |  <span data-ttu-id="c3d80-114">CompanyCode</span><span class="sxs-lookup"><span data-stu-id="c3d80-114">CompanyCode</span></span>  |    <span data-ttu-id="c3d80-115">CompanyCode</span><span class="sxs-lookup"><span data-stu-id="c3d80-115">CompanyCode</span></span>     |
   |    <span data-ttu-id="c3d80-116">PartId</span><span class="sxs-lookup"><span data-stu-id="c3d80-116">PartId</span></span>     |      <span data-ttu-id="c3d80-117">PartNum</span><span class="sxs-lookup"><span data-stu-id="c3d80-117">PartNum</span></span>       |
   |   <span data-ttu-id="c3d80-118">Quantity</span><span class="sxs-lookup"><span data-stu-id="c3d80-118">Quantity</span></span>    |        <span data-ttu-id="c3d80-119">Qty</span><span class="sxs-lookup"><span data-stu-id="c3d80-119">Qty</span></span>         |
   |   <span data-ttu-id="c3d80-120">AskPrice</span><span class="sxs-lookup"><span data-stu-id="c3d80-120">AskPrice</span></span>    |    <span data-ttu-id="c3d80-121">UnitAskPrice</span><span class="sxs-lookup"><span data-stu-id="c3d80-121">UnitAskPrice</span></span>    |
   |   <span data-ttu-id="c3d80-122">注释</span><span class="sxs-lookup"><span data-stu-id="c3d80-122">Comments</span></span>    |  <span data-ttu-id="c3d80-123">CustomerComments</span><span class="sxs-lookup"><span data-stu-id="c3d80-123">CustomerComments</span></span>  |


4. <span data-ttu-id="c3d80-124">使用**日期和时间**functoid 以将值映射到**DateRequested**并**ShipDate**目标架构中的元素。</span><span class="sxs-lookup"><span data-stu-id="c3d80-124">Use the **Date and Time** functoid to map values to the **DateRequested** and **ShipDate** elements in the destination schema.</span></span> <span data-ttu-id="c3d80-125">这些节点将不会映射到源架构中的各个节点，</span><span class="sxs-lookup"><span data-stu-id="c3d80-125">These nodes are not mapped to the respective nodes in the source schema.</span></span> <span data-ttu-id="c3d80-126">相反，当前日期和时间传递到这些节点通过使用**日期和时间**functoid。</span><span class="sxs-lookup"><span data-stu-id="c3d80-126">Instead, the current date and time is passed on to these nodes by using the **Date and Time** functoid.</span></span>  

   1.  <span data-ttu-id="c3d80-127">拖放到**日期和时间**functoid 从工具箱拖到映射器图面。</span><span class="sxs-lookup"><span data-stu-id="c3d80-127">Drag and drop a **Date and Time** functoid from toolbox to the mapper surface.</span></span>  

   2.  <span data-ttu-id="c3d80-128">连接到 functoid **DateRequested**目标架构中的元素。</span><span class="sxs-lookup"><span data-stu-id="c3d80-128">Connect the functoid to the **DateRequested** element in the destination schema.</span></span>  

   3.  <span data-ttu-id="c3d80-129">拖放另一个**日期和时间**functoid 并将其连接到**ShipDate**目标架构中的元素。</span><span class="sxs-lookup"><span data-stu-id="c3d80-129">Drag and drop another **Date and Time** functoid and connect it to the **ShipDate** element in the destination schema.</span></span>  

5. <span data-ttu-id="c3d80-130">映射使用源和目标架构中的以下节点**字符串连接**functoid:</span><span class="sxs-lookup"><span data-stu-id="c3d80-130">Map the following nodes in the source and destination schemas using a **String Concatenate** functoid:</span></span>  

   |<span data-ttu-id="c3d80-131">源架构</span><span class="sxs-lookup"><span data-stu-id="c3d80-131">Source Schema</span></span>|<span data-ttu-id="c3d80-132">目标架构</span><span class="sxs-lookup"><span data-stu-id="c3d80-132">Destination Schema</span></span>|  
   |-------------------|------------------------|  
   |<span data-ttu-id="c3d80-133">Address\Line1</span><span class="sxs-lookup"><span data-stu-id="c3d80-133">Address\Line1</span></span>|<span data-ttu-id="c3d80-134">SellToAddress</span><span class="sxs-lookup"><span data-stu-id="c3d80-134">SellToAddress</span></span><br /><br /> <span data-ttu-id="c3d80-135">BillToAddress</span><span class="sxs-lookup"><span data-stu-id="c3d80-135">BillToAddress</span></span>|  
   |<span data-ttu-id="c3d80-136">Address\Line2</span><span class="sxs-lookup"><span data-stu-id="c3d80-136">Address\Line2</span></span>|<span data-ttu-id="c3d80-137">SellToAddress</span><span class="sxs-lookup"><span data-stu-id="c3d80-137">SellToAddress</span></span><br /><br /> <span data-ttu-id="c3d80-138">BillToAddress</span><span class="sxs-lookup"><span data-stu-id="c3d80-138">BillToAddress</span></span>|  
   |<span data-ttu-id="c3d80-139">Address\City</span><span class="sxs-lookup"><span data-stu-id="c3d80-139">Address\City</span></span>|<span data-ttu-id="c3d80-140">SellToAddress</span><span class="sxs-lookup"><span data-stu-id="c3d80-140">SellToAddress</span></span><br /><br /> <span data-ttu-id="c3d80-141">BillToAddress</span><span class="sxs-lookup"><span data-stu-id="c3d80-141">BillToAddress</span></span>|  
   |<span data-ttu-id="c3d80-142">Address\State</span><span class="sxs-lookup"><span data-stu-id="c3d80-142">Address\State</span></span>|<span data-ttu-id="c3d80-143">SellToAddress</span><span class="sxs-lookup"><span data-stu-id="c3d80-143">SellToAddress</span></span><br /><br /> <span data-ttu-id="c3d80-144">BillToAddress</span><span class="sxs-lookup"><span data-stu-id="c3d80-144">BillToAddress</span></span>|  
   |<span data-ttu-id="c3d80-145">Address\Country</span><span class="sxs-lookup"><span data-stu-id="c3d80-145">Address\Country</span></span>|<span data-ttu-id="c3d80-146">SellToAddress</span><span class="sxs-lookup"><span data-stu-id="c3d80-146">SellToAddress</span></span><br /><br /> <span data-ttu-id="c3d80-147">BillToAddress</span><span class="sxs-lookup"><span data-stu-id="c3d80-147">BillToAddress</span></span>|  
   |<span data-ttu-id="c3d80-148">Address\ZipCode</span><span class="sxs-lookup"><span data-stu-id="c3d80-148">Address\ZipCode</span></span>|<span data-ttu-id="c3d80-149">SellToAddress</span><span class="sxs-lookup"><span data-stu-id="c3d80-149">SellToAddress</span></span><br /><br /> <span data-ttu-id="c3d80-150">BillToAddress</span><span class="sxs-lookup"><span data-stu-id="c3d80-150">BillToAddress</span></span>|  
   |<span data-ttu-id="c3d80-151">Contact\FirstName</span><span class="sxs-lookup"><span data-stu-id="c3d80-151">Contact\FirstName</span></span>|<span data-ttu-id="c3d80-152">PartnerContact</span><span class="sxs-lookup"><span data-stu-id="c3d80-152">PartnerContact</span></span>|  
   |<span data-ttu-id="c3d80-153">Contact\LastName</span><span class="sxs-lookup"><span data-stu-id="c3d80-153">Contact\LastName</span></span>||  

    <span data-ttu-id="c3d80-154">对每个字符串连接映射集执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="c3d80-154">Perform the following steps for each of the string concatenation mapping sets:</span></span>  

   1.  <span data-ttu-id="c3d80-155">拖放到**字符串连接**functoid 从工具箱拖到映射器图面。</span><span class="sxs-lookup"><span data-stu-id="c3d80-155">Drag and drop a **String Concatenate** functoid from toolbox to the mapper surface.</span></span>  

   2.  <span data-ttu-id="c3d80-156">将源树中的每个元素添加为的输入**字符串连接**functoid。</span><span class="sxs-lookup"><span data-stu-id="c3d80-156">Add each element from the source tree as an input to the **String Concatenate** functoid.</span></span>  

   3.  <span data-ttu-id="c3d80-157">拖放到配置的输出**字符串连接**functoid 到目标架构中的元素。</span><span class="sxs-lookup"><span data-stu-id="c3d80-157">Drag and configure the output of the **String Concatenate** functoid to the element in the destination schema.</span></span>  

        <span data-ttu-id="c3d80-158">设置好的映射类似于以下内容：</span><span class="sxs-lookup"><span data-stu-id="c3d80-158">The completed map resembles the following:</span></span>  

        <span data-ttu-id="c3d80-159">![映射到转换架构](../core/media/bts2010r2-tut1-map.jpg "BTS2010R2_Tut1_Map")</span><span class="sxs-lookup"><span data-stu-id="c3d80-159">![Map to transform schemas](../core/media/bts2010r2-tut1-map.jpg "BTS2010R2_Tut1_Map")</span></span>  

## <a name="see-also"></a><span data-ttu-id="c3d80-160">请参阅</span><span class="sxs-lookup"><span data-stu-id="c3d80-160">See Also</span></span>  
 [<span data-ttu-id="c3d80-161">教程 4： 创建混合应用程序使用 BizTalk Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3d80-161">Tutorial 4: Creating a Hybrid Application Using BizTalk Server 2013</span></span>](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)