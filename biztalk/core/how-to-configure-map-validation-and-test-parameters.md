---
title: 如何配置映射验证和测试参数 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1768918c-e94f-476f-b288-9e030c691177
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e7aaa62e74f1c49f2e43d96c7d546af023847d91
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967406"
---
# <a name="how-to-configure-map-validation-and-test-parameters"></a><span data-ttu-id="97d3a-102">如何配置映射验证和测试参数</span><span class="sxs-lookup"><span data-stu-id="97d3a-102">How to Configure Map Validation and Test Parameters</span></span>
<span data-ttu-id="97d3a-103">需要设置映射验证和测试参数在验证和测试映射前,**属性**映射的窗口。</span><span class="sxs-lookup"><span data-stu-id="97d3a-103">Before validating and testing a map, you need to set the map validation and test parameters in the **Properties** window of the map.</span></span>  
  
## <a name="configure-the-map-validation-and-test-parameters"></a><span data-ttu-id="97d3a-104">配置映射验证和测试参数</span><span class="sxs-lookup"><span data-stu-id="97d3a-104">Configure the map validation and test parameters</span></span>  
  
1.  <span data-ttu-id="97d3a-105">在解决方案资源管理器，右键单击映射其属性页，你想要配置，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="97d3a-105">In Solution Explorer, right-click the map whose property pages you want to configure, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="97d3a-106">在“属性”窗口中，执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="97d3a-106">In the Properties window, do the following.</span></span>  
  
    |<span data-ttu-id="97d3a-107">使用此选项</span><span class="sxs-lookup"><span data-stu-id="97d3a-107">Use this</span></span>|<span data-ttu-id="97d3a-108">执行的操作</span><span class="sxs-lookup"><span data-stu-id="97d3a-108">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="97d3a-109">**验证测试映射输入**</span><span class="sxs-lookup"><span data-stu-id="97d3a-109">**Validate TestMap Input**</span></span>|<span data-ttu-id="97d3a-110">配置在测试映射前是否根据源架构验证实例消息。</span><span class="sxs-lookup"><span data-stu-id="97d3a-110">Configure whether you want to have the instance message validated against the source schema before you test the map.</span></span>|  
    |<span data-ttu-id="97d3a-111">**验证测试映射输出**</span><span class="sxs-lookup"><span data-stu-id="97d3a-111">**Validate TestMap Output**</span></span>|<span data-ttu-id="97d3a-112">配置在测试映射后是否根据目标架构验证实例消息。</span><span class="sxs-lookup"><span data-stu-id="97d3a-112">Configure whether you want to have the instance message validated against the destination schema after you test the map.</span></span>|  
    |<span data-ttu-id="97d3a-113">**测试映射输入实例**</span><span class="sxs-lookup"><span data-stu-id="97d3a-113">**TestMap Input Instance**</span></span>|<span data-ttu-id="97d3a-114">配置测试映射时要使用的实例消息数据的位置。</span><span class="sxs-lookup"><span data-stu-id="97d3a-114">Configure the location of the instance message data to use when you test the map.</span></span><br /><br /> <span data-ttu-id="97d3a-115">如果配置此属性，则还必须配置**测试映射输入**属性。</span><span class="sxs-lookup"><span data-stu-id="97d3a-115">If you configure this property, you must also configure the **TestMap Input** property.</span></span>|  
    |<span data-ttu-id="97d3a-116">**测试映射输出实例**</span><span class="sxs-lookup"><span data-stu-id="97d3a-116">**TestMap Output Instance**</span></span>|<span data-ttu-id="97d3a-117">配置您希望将测试映射操作输出要存储到的文件位置。</span><span class="sxs-lookup"><span data-stu-id="97d3a-117">Configure the location of the file where you want the output of the test map operation to be stored.</span></span><br /><br /> <span data-ttu-id="97d3a-118">如果配置此属性，则还必须配置**测试映射输出**属性。</span><span class="sxs-lookup"><span data-stu-id="97d3a-118">If you configure this property, you must also configure the **TestMap Output** property.</span></span>|  
    |<span data-ttu-id="97d3a-119">**测试映射输入**</span><span class="sxs-lookup"><span data-stu-id="97d3a-119">**TestMap Input**</span></span>|<span data-ttu-id="97d3a-120">配置输入实例数据格式。</span><span class="sxs-lookup"><span data-stu-id="97d3a-120">Configure the input instance data format.</span></span>|  
    |<span data-ttu-id="97d3a-121">**测试映射输出**</span><span class="sxs-lookup"><span data-stu-id="97d3a-121">**TestMap Output**</span></span>|<span data-ttu-id="97d3a-122">配置测试映射时要使用的输出数据类型。</span><span class="sxs-lookup"><span data-stu-id="97d3a-122">Configure the output data type to use when you test the map.</span></span>|  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="97d3a-123">如果要测试映射，必须先配置映射属性。</span><span class="sxs-lookup"><span data-stu-id="97d3a-123">If you want to test your map, you must configure the map properties first.</span></span>  

<span data-ttu-id="97d3a-124">开发映射后，接下来的步骤之一是对其进行验证。</span><span class="sxs-lookup"><span data-stu-id="97d3a-124">After you have developed your map, one of the next steps is to validate it.</span></span> <span data-ttu-id="97d3a-125">本主题提供用于验证映射的分步说明。</span><span class="sxs-lookup"><span data-stu-id="97d3a-125">This topic provides step-by-step instructions for validating maps.</span></span>  
  
## <a name="validate-a-biztalk-map"></a><span data-ttu-id="97d3a-126">验证 BizTalk 映射</span><span class="sxs-lookup"><span data-stu-id="97d3a-126">Validate a BizTalk map</span></span>  
  
1.  <span data-ttu-id="97d3a-127">在解决方案资源管理器，打开你想要验证的映射。</span><span class="sxs-lookup"><span data-stu-id="97d3a-127">In Solution Explorer, open the map that you want to validate.</span></span>  
  
2.  <span data-ttu-id="97d3a-128">在解决方案资源管理器，右键单击该映射，然后选择**验证映射**。</span><span class="sxs-lookup"><span data-stu-id="97d3a-128">In Solution Explorer, right-click the map, and then select **Validate Map**.</span></span>  
  
3.  <span data-ttu-id="97d3a-129">在中**输出**窗口中，验证结果。</span><span class="sxs-lookup"><span data-stu-id="97d3a-129">In the **Output** window, verify the results.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="97d3a-130">如果在输出中使用自定义数据或常量，则必须验证您的源的数据类型的测试数据和目标的常量值有效。</span><span class="sxs-lookup"><span data-stu-id="97d3a-130">If you use custom data or constants in your output, you must verify that the data types of your source test data and target constant values are valid.</span></span> <span data-ttu-id="97d3a-131">验证映射时，BizTalk 映射器不会检查实例数据是否违反了架构中定义的任何数据类型。</span><span class="sxs-lookup"><span data-stu-id="97d3a-131">When you validate a map, BizTalk Mapper does not check if the instance data violates any data types defined in the schemas.</span></span> <span data-ttu-id="97d3a-132">这是测试映射或验证实例数据使用 BizTalk 编辑器时。</span><span class="sxs-lookup"><span data-stu-id="97d3a-132">This is done when you test the map or validate the instance data with BizTalk Editor.</span></span> 

## <a name="test-a-biztalk-map"></a><span data-ttu-id="97d3a-133">测试 BizTalk 映射</span><span class="sxs-lookup"><span data-stu-id="97d3a-133">Test a BizTalk map</span></span>

<span data-ttu-id="97d3a-134">开发映射后要执行的步骤之一即是对其进行测试。</span><span class="sxs-lookup"><span data-stu-id="97d3a-134">After you have developed your map, one of the next steps is to test it.</span></span> <span data-ttu-id="97d3a-135">本主题提供有关测试映射的分步说明，其中包括有关查看映射编译器所生成的 XSLT 的步骤的说明。</span><span class="sxs-lookup"><span data-stu-id="97d3a-135">This topic provides step-by-step instructions for testing maps including steps to view the XSLT generated by the map compiler.</span></span>  
  
1.  <span data-ttu-id="97d3a-136">在解决方案资源管理器，右键单击你想要测试，然后选择的映射**测试映射**。</span><span class="sxs-lookup"><span data-stu-id="97d3a-136">In Solution Explorer, right-click the map you want to test, and then select **Test Map**.</span></span>  
  
2.  <span data-ttu-id="97d3a-137">验证结果的**输出**窗口。</span><span class="sxs-lookup"><span data-stu-id="97d3a-137">Verify the results in the **Output** window.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="97d3a-138">建议您先在“属性”窗口中配置输入和输出实例属性，然后再测试映射。</span><span class="sxs-lookup"><span data-stu-id="97d3a-138">It is recommended that you configure the input and output instance properties in the Properties window before you test a map.</span></span>  
  
## <a name="review-the-xslt"></a><span data-ttu-id="97d3a-139">查看 XSLT</span><span class="sxs-lookup"><span data-stu-id="97d3a-139">Review the XSLT</span></span>  
 <span data-ttu-id="97d3a-140">通常它可用于检查映射编译器生成的 XSLT。</span><span class="sxs-lookup"><span data-stu-id="97d3a-140">It is often useful to inspect the XSLT generated by the map compiler.</span></span> <span data-ttu-id="97d3a-141">检查 XSLT 的优势包括：</span><span class="sxs-lookup"><span data-stu-id="97d3a-141">Some of the benefits of inspecting XSLT include:</span></span>  
  
- <span data-ttu-id="97d3a-142">如果使用循环或自定义 functoid 时，将更好地了解如何执行循环和如何调用自定义 functoid。</span><span class="sxs-lookup"><span data-stu-id="97d3a-142">If you are using looping or custom functoids, you will better understand how the looping is performed and how the custom functoid is invoked.</span></span>  
  
- <span data-ttu-id="97d3a-143">如果你具有复杂的代码图，查看 XSLT 将允许您看到如何映射翻译为转换，并可能会为您提供见解如何更好地构造、 替换或简化一个或多个部分。</span><span class="sxs-lookup"><span data-stu-id="97d3a-143">If you have a complicated map, reviewing the XSLT will enable you to see how the map is translated into a transform, and may give you insight on how to better structure, replace, or streamline one or more parts.</span></span>  
  
- <span data-ttu-id="97d3a-144">如果使用自定义脚本或其他项目，查看 XSLT 便可以看到脚本、 项目和映射的其他部分的交互方式。</span><span class="sxs-lookup"><span data-stu-id="97d3a-144">If you are using custom scripts or other artifacts, reviewing the XSLT will enable you to see how the scripts, artifacts, and other parts of the map interact.</span></span>  
  
  <span data-ttu-id="97d3a-145">换而言之，查看 XSLT 是调试映射的好办法。</span><span class="sxs-lookup"><span data-stu-id="97d3a-145">In other words, reviewing the XSLT is a great way to debug a map.</span></span>  
  
#### <a name="view-the-xslt-generated-by-the-map-compiler"></a><span data-ttu-id="97d3a-146">查看映射编译器所生成的 XSLT</span><span class="sxs-lookup"><span data-stu-id="97d3a-146">View the XSLT generated by the map compiler</span></span>  
  
1.  <span data-ttu-id="97d3a-147">从 Visual Studio BizTalk 项目中，选择**解决方案资源管理器**选项卡上，右键单击映射，并选择**验证映射**。</span><span class="sxs-lookup"><span data-stu-id="97d3a-147">From a Visual Studio BizTalk project, select the **Solution Explorer** tab, right-click a map, and then select **Validate Map**.</span></span>  
  
2.  <span data-ttu-id="97d3a-148">滚动输出窗口以查找 XSL 文件的 URL。</span><span class="sxs-lookup"><span data-stu-id="97d3a-148">Scroll the Output window to find the URL for the XSL file.</span></span> <span data-ttu-id="97d3a-149">按**CTRL**，然后选择要查看该文件的 URL。</span><span class="sxs-lookup"><span data-stu-id="97d3a-149">Press **CTRL**, and select the URL to view the file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="97d3a-150">对 XSL 文件所做的更改不会反映在映射中，并在下一个生成上覆盖。</span><span class="sxs-lookup"><span data-stu-id="97d3a-150">Changes made to the XSL file are not reflected in the map and are overwritten on the next build.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97d3a-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="97d3a-151">See also</span></span>  

[<span data-ttu-id="97d3a-152">如何调试映射</span><span class="sxs-lookup"><span data-stu-id="97d3a-152">How to Debug Maps</span></span>](../core/how-to-debug-maps.md)  
[<span data-ttu-id="97d3a-153">排除地图故障</span><span class="sxs-lookup"><span data-stu-id="97d3a-153">Troubleshooting Maps</span></span>](../core/troubleshooting-maps.md)  