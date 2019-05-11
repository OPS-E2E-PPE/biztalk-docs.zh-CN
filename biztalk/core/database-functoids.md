---
title: 数据库 Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 77bc9390-cdb5-42ff-8b28-6265c51c79fc
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 63709f5857e7d05d4739f5cdcc62916ed5891f9c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389954"
---
# <a name="database-functoids"></a><span data-ttu-id="015f2-102">数据库 Functoid</span><span class="sxs-lookup"><span data-stu-id="015f2-102">Database Functoids</span></span>
<span data-ttu-id="015f2-103">**数据库**functoid 从输出实例消息中使用的数据库中提取数据。</span><span class="sxs-lookup"><span data-stu-id="015f2-103">**Database** functoids extract data from a database for use in an output instance message.</span></span> 

## <a name="overview"></a><span data-ttu-id="015f2-104">概述</span><span class="sxs-lookup"><span data-stu-id="015f2-104">Overview</span></span>
<span data-ttu-id="015f2-105">以下是一系列**数据库**functoid 以及如何使用它们：</span><span class="sxs-lookup"><span data-stu-id="015f2-105">The following is a list of the **Database** functoids and how you can use them:</span></span>  

- <span data-ttu-id="015f2-106">**数据库查找。**</span><span class="sxs-lookup"><span data-stu-id="015f2-106">**Database Lookup.**</span></span> <span data-ttu-id="015f2-107">使用**数据库查找**functoid 从数据库中提取信息并将其存储为 Microsoft ActiveX 数据对象.NET (ADO.NET) 记录集。</span><span class="sxs-lookup"><span data-stu-id="015f2-107">Use the **Database Lookup** functoid to extract information from a database and store it as a Microsoft ActiveX Data Objects .NET (ADO.NET) recordset.</span></span> <span data-ttu-id="015f2-108">此 functoid 需要按以下顺序的四个输入的参数：</span><span class="sxs-lookup"><span data-stu-id="015f2-108">This functoid requires four input parameters in the following order:</span></span>  

  -   <span data-ttu-id="015f2-109">查找值</span><span class="sxs-lookup"><span data-stu-id="015f2-109">A lookup value</span></span>  

  -   <span data-ttu-id="015f2-110">数据库连接字符串</span><span class="sxs-lookup"><span data-stu-id="015f2-110">A database connection string</span></span>  

  -   <span data-ttu-id="015f2-111">表名称</span><span class="sxs-lookup"><span data-stu-id="015f2-111">A table name</span></span>  

  -   <span data-ttu-id="015f2-112">查找值的列名称。</span><span class="sxs-lookup"><span data-stu-id="015f2-112">A column name for the lookup value.</span></span>  

- <span data-ttu-id="015f2-113">**错误返回。**</span><span class="sxs-lookup"><span data-stu-id="015f2-113">**Error Return.**</span></span> <span data-ttu-id="015f2-114">使用**错误返回**functoid 来捕获错误信息，例如数据库连接失败，在运行时出现。</span><span class="sxs-lookup"><span data-stu-id="015f2-114">Use the **Error Return** functoid to capture error information, such as database connection failures, that occur during run time.</span></span> <span data-ttu-id="015f2-115">此 functoid 需要一个输入的参数： 从链接**数据库查找**functoid。</span><span class="sxs-lookup"><span data-stu-id="015f2-115">This functoid requires one input parameter: a link from the **Database Lookup** functoid.</span></span>  

- <span data-ttu-id="015f2-116">**格式化消息。**</span><span class="sxs-lookup"><span data-stu-id="015f2-116">**Format Message.**</span></span> <span data-ttu-id="015f2-117">返回格式化和本地化的字符串，使用参数替换，以及可能的 ID 和值的交叉引用。</span><span class="sxs-lookup"><span data-stu-id="015f2-117">Returns a formatted and localized string using argument substitution and, potentially, ID and value cross-referencing.</span></span>  

- <span data-ttu-id="015f2-118">**获取应用程序 id。**</span><span class="sxs-lookup"><span data-stu-id="015f2-118">**Get Application ID.**</span></span> <span data-ttu-id="015f2-119">检索应用程序对象的标识符。</span><span class="sxs-lookup"><span data-stu-id="015f2-119">Retrieves an identifier for an application object.</span></span>  

- <span data-ttu-id="015f2-120">**获取应用程序值。**</span><span class="sxs-lookup"><span data-stu-id="015f2-120">**Get Application Value.**</span></span> <span data-ttu-id="015f2-121">检索应用程序值。</span><span class="sxs-lookup"><span data-stu-id="015f2-121">Retrieves an application value.</span></span>  

- <span data-ttu-id="015f2-122">**获取公用 id。**</span><span class="sxs-lookup"><span data-stu-id="015f2-122">**Get Common ID.**</span></span> <span data-ttu-id="015f2-123">检索公用对象标识符。</span><span class="sxs-lookup"><span data-stu-id="015f2-123">Retrieves an identifier for a common object.</span></span>  

- <span data-ttu-id="015f2-124">**获取公用值。**</span><span class="sxs-lookup"><span data-stu-id="015f2-124">**Get Common Value.**</span></span> <span data-ttu-id="015f2-125">检索公用值。</span><span class="sxs-lookup"><span data-stu-id="015f2-125">Retrieves a common value.</span></span>  

- <span data-ttu-id="015f2-126">**删除应用程序 id。**</span><span class="sxs-lookup"><span data-stu-id="015f2-126">**Remove Application ID.**</span></span> <span data-ttu-id="015f2-127">删除应用程序值。</span><span class="sxs-lookup"><span data-stu-id="015f2-127">Removes an application value.</span></span>  

- <span data-ttu-id="015f2-128">**设置公用 id。**</span><span class="sxs-lookup"><span data-stu-id="015f2-128">**Set Common ID.**</span></span> <span data-ttu-id="015f2-129">设置和返回公用对象标识符。</span><span class="sxs-lookup"><span data-stu-id="015f2-129">Sets and returns an identifier for a common object.</span></span>  

- <span data-ttu-id="015f2-130">**值提取程序。**</span><span class="sxs-lookup"><span data-stu-id="015f2-130">**Value Extractor.**</span></span> <span data-ttu-id="015f2-131">使用**值提取程序**functoid 来提取数据，从指定列中返回的记录集**数据库查找**functoid。</span><span class="sxs-lookup"><span data-stu-id="015f2-131">Use the **Value Extractor** functoid to extract data from the specified column in a recordset returned by the **Database Lookup** functoid.</span></span> <span data-ttu-id="015f2-132">该 functoid 需要两个输入参数： 一个指向**数据库查找**functoid 和列名称。</span><span class="sxs-lookup"><span data-stu-id="015f2-132">This functoid requires two input parameters: a link to the **Database Lookup** functoid and a column name.</span></span>  

  <span data-ttu-id="015f2-133">七**数据库**functoid —**格式化消息、 获取应用程序 ID**，**获取应用程序值**，**获取公用 ID**， **获取公用值**，**删除应用程序 ID**，并**设置公用 ID**— 是**CrossReferencing** functoid。</span><span class="sxs-lookup"><span data-stu-id="015f2-133">Seven of the **Database** functoids— **Format Message, Get Application ID**, **Get Application Value**, **Get Common ID**, **Get Common Value**, **Remove Application ID**, and **Set Common ID**—are **CrossReferencing** functoids.</span></span> <span data-ttu-id="015f2-134">这些 functoid 转换为的 Id 和值从输入消息的 Id 和输出消息中所需值。</span><span class="sxs-lookup"><span data-stu-id="015f2-134">These functoids translate IDs and values from an input message into the IDs and values needed in the output message.</span></span> <span data-ttu-id="015f2-135">有关详细信息，请参阅**Database Functoids Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="015f2-135">For more information, see **Database Functoids Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span> 

## <a name="example"></a><span data-ttu-id="015f2-136">示例</span><span class="sxs-lookup"><span data-stu-id="015f2-136">Example</span></span>  
 <span data-ttu-id="015f2-137">下面的示例使用的一些**数据库**functoid。</span><span class="sxs-lookup"><span data-stu-id="015f2-137">The following example uses some of the **Database** functoids.</span></span> <span data-ttu-id="015f2-138">与存储跨越较大的地理区域，请考虑一个大型零售制造商。</span><span class="sxs-lookup"><span data-stu-id="015f2-138">Consider a large retail manufacturer with stores spread over a large geographical area.</span></span> <span data-ttu-id="015f2-139">若要跟踪的存储，总部，将分配唯一的代码调用每个应用商店**StoreID**。</span><span class="sxs-lookup"><span data-stu-id="015f2-139">To keep track of the stores, headquarters assigns each store a unique code called a **StoreID**.</span></span> <span data-ttu-id="015f2-140">此外，总部将以下信息与每个相关联**StoreID**:</span><span class="sxs-lookup"><span data-stu-id="015f2-140">Additionally, headquarters associates the following information with each **StoreID**:</span></span>  

- <span data-ttu-id="015f2-141">StoreName</span><span class="sxs-lookup"><span data-stu-id="015f2-141">StoreName</span></span>  

- <span data-ttu-id="015f2-142">StoreAddress</span><span class="sxs-lookup"><span data-stu-id="015f2-142">StoreAddress</span></span>  

- <span data-ttu-id="015f2-143">City</span><span class="sxs-lookup"><span data-stu-id="015f2-143">City</span></span>  

- <span data-ttu-id="015f2-144">PostalCode</span><span class="sxs-lookup"><span data-stu-id="015f2-144">PostalCode</span></span>  

- <span data-ttu-id="015f2-145">StorePhoneNumber</span><span class="sxs-lookup"><span data-stu-id="015f2-145">StorePhoneNumber</span></span>  

- <span data-ttu-id="015f2-146">StoreManager</span><span class="sxs-lookup"><span data-stu-id="015f2-146">StoreManager</span></span>  

  <span data-ttu-id="015f2-147">此信息存储在数据库和分发给贸易合作伙伴定期进行。</span><span class="sxs-lookup"><span data-stu-id="015f2-147">This information is stored in a database and is distributed to trading partners on a regular basis.</span></span> <span data-ttu-id="015f2-148">对于该制造商来说，所有购买是总部完成的不是各个商店。</span><span class="sxs-lookup"><span data-stu-id="015f2-148">For the manufacturer, all purchasing is done by headquarters, not the stores.</span></span> <span data-ttu-id="015f2-149">当总部向贸易合作伙伴发送采购订单时，很常见的多个商店可以收到通过该采购订单订购的商品。</span><span class="sxs-lookup"><span data-stu-id="015f2-149">When headquarters sends a purchase order to the trading partners, it is common for multiple stores to receive merchandise ordered through the single purchase order.</span></span> <span data-ttu-id="015f2-150">而不是发送为每个要接收商品的商店名称和地址信息，总部只需发送**StoreID**。</span><span class="sxs-lookup"><span data-stu-id="015f2-150">Instead of sending name and address information for each store that is to receive merchandise, headquarters simply sends the **StoreID**.</span></span> <span data-ttu-id="015f2-151">若要提前的发运通知中插入名称和地址信息，贸易合作伙伴可使用**数据库**functoid 以自动将此信息插入到输出实例消息。</span><span class="sxs-lookup"><span data-stu-id="015f2-151">To insert the name and address information into the advanced ship notice, the trading partner uses the **Database** functoids to automatically insert this information into the output instance message.</span></span> <span data-ttu-id="015f2-152">下图显示了贸易合作伙伴如何在映射中实施 StoreID 替换。</span><span class="sxs-lookup"><span data-stu-id="015f2-152">The following figure shows how a trading partner can implement the replacement of the StoreID in a map.</span></span>  

  <span data-ttu-id="015f2-153">![将显示不同数据库 functoid 的映射。](../core/media/origdbfunctoids.gif "origdbfunctoids")</span><span class="sxs-lookup"><span data-stu-id="015f2-153">![Map showing  different database functoids.](../core/media/origdbfunctoids.gif "origdbfunctoids")</span></span>  

  <span data-ttu-id="015f2-154">在图中，源架构代表传入采购订单;目标架构则代表提前的发运通知。</span><span class="sxs-lookup"><span data-stu-id="015f2-154">In the figure, the source schema represents an incoming purchase order; the destination schema represents an advanced ship notice.</span></span> <span data-ttu-id="015f2-155">**数据库查找**functoid 查找相应的数据库表中相应的记录。</span><span class="sxs-lookup"><span data-stu-id="015f2-155">The **Database Lookup** functoid finds the appropriate record from the appropriate database table.</span></span> <span data-ttu-id="015f2-156">**值提取程序**functoid 从查找记录中提取相应的列。</span><span class="sxs-lookup"><span data-stu-id="015f2-156">The **Value Extractor** functoids extract the appropriate column from the lookup record.</span></span> <span data-ttu-id="015f2-157">**错误返回**functoid 在运行时输出一个字符串，包含错误的信息，如果有错误 （如连接失败）。</span><span class="sxs-lookup"><span data-stu-id="015f2-157">The **Error Return** functoid outputs a string containing error information if there are errors (such as connection failures) at run time.</span></span>  

  <span data-ttu-id="015f2-158">在上一示例中，第一个输入的参数取自**StoreID**字段传入的采购订单，和剩余三个输入参数中配置的常数**配置\<Functoid\> Functoid**对话框**数据库查找**functoid。</span><span class="sxs-lookup"><span data-stu-id="015f2-158">In the previous example, the first input parameter is taken from the **StoreID** field of the incoming purchase order, and the remaining three input parameters are constants configured in the **Configure \<Functoid\> Functoid** dialog box for the **Database Lookup** functoid.</span></span> <span data-ttu-id="015f2-159">就可以从要为所有四个输入参数提供值的源架构中创建的链接。</span><span class="sxs-lookup"><span data-stu-id="015f2-159">It is possible to create links from the source schema to supply values for all four input parameters.</span></span>  

> [!NOTE]
>  * <span data-ttu-id="015f2-160">不能使用某些 Microsoft SQL Server 数据类型，例如**文本**， **ntext**，并**图像**，查找值的形式**数据库查找**functoid。</span><span class="sxs-lookup"><span data-stu-id="015f2-160">You cannot use some Microsoft SQL Server data types, such as **text**, **ntext**, and **image**, as lookup values for the **Database Lookup** functoid.</span></span> <span data-ttu-id="015f2-161">该 functoid 需要可以表示为文本字符串的数据类型。</span><span class="sxs-lookup"><span data-stu-id="015f2-161">The functoid requires data types that can be represented as a text string.</span></span>  
>
>  * <span data-ttu-id="015f2-162">如果没有匹配的输入的参数的多个记录**数据库查找**functoid**值提取程序**functoid 只从第一条记录中提取数据。</span><span class="sxs-lookup"><span data-stu-id="015f2-162">If there is more than one record matching the input parameters of the **Database Lookup** functoid, the **Value Extractor** functoid extracts data only from the first record.</span></span>  
>
>  * <span data-ttu-id="015f2-163">若要保护密码和加密的连接字符串中使用 NT 身份验证。</span><span class="sxs-lookup"><span data-stu-id="015f2-163">Use NT authentication in connection strings to protect passwords with encryption.</span></span>  

## <a name="available-functoids"></a><span data-ttu-id="015f2-164">可用的 functoid</span><span class="sxs-lookup"><span data-stu-id="015f2-164">Available functoids</span></span>  
 <span data-ttu-id="015f2-165">**数据库**functoid 包括：</span><span class="sxs-lookup"><span data-stu-id="015f2-165">The **Database** functoids are:</span></span> 

* <span data-ttu-id="015f2-166">数据库查找</span><span class="sxs-lookup"><span data-stu-id="015f2-166">Database Lookup</span></span>
* <span data-ttu-id="015f2-167">错误返回</span><span class="sxs-lookup"><span data-stu-id="015f2-167">Error Return</span></span>
* <span data-ttu-id="015f2-168">格式化消息</span><span class="sxs-lookup"><span data-stu-id="015f2-168">Format Message</span></span>
* <span data-ttu-id="015f2-169">获取应用程序 ID</span><span class="sxs-lookup"><span data-stu-id="015f2-169">Get Application ID</span></span>
* <span data-ttu-id="015f2-170">获取应用程序值</span><span class="sxs-lookup"><span data-stu-id="015f2-170">Get Application Value</span></span>
* <span data-ttu-id="015f2-171">获取公用 ID</span><span class="sxs-lookup"><span data-stu-id="015f2-171">Get Common ID</span></span>
* <span data-ttu-id="015f2-172">获取公用值</span><span class="sxs-lookup"><span data-stu-id="015f2-172">Get Common Value</span></span>
* <span data-ttu-id="015f2-173">删除应用程序 ID</span><span class="sxs-lookup"><span data-stu-id="015f2-173">Remove Application ID</span></span>
* <span data-ttu-id="015f2-174">设置公用 ID</span><span class="sxs-lookup"><span data-stu-id="015f2-174">Set Common ID</span></span>
* <span data-ttu-id="015f2-175">值提取程序</span><span class="sxs-lookup"><span data-stu-id="015f2-175">Value Extractor</span></span>

<span data-ttu-id="015f2-176">有关这些 functiods 的更多详细信息，请参阅**Functoid 参考** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="015f2-176">For more details on these functiods, see the **Functoid Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>

## <a name="see-also"></a><span data-ttu-id="015f2-177">请参阅</span><span class="sxs-lookup"><span data-stu-id="015f2-177">See Also</span></span>  
- [<span data-ttu-id="015f2-178">如何向映射添加基本 Functoid</span><span class="sxs-lookup"><span data-stu-id="015f2-178">How to Add Basic Functoids to a Map</span></span>](../core/how-to-add-basic-functoids-to-a-map.md)   
- <span data-ttu-id="015f2-179">**数据库 Functoid 参考** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="015f2-179">**Database Functoids Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
