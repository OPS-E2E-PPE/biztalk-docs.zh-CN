---
title: 请求集的操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0537354d-821e-4cf9-a4d1-f4e7d1643df9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cfc8c773be09a302e740b2eb7d59828e3a1688b4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375296"
---
# <a name="operations-on-request-sets"></a><span data-ttu-id="dce7e-102">请求集的操作</span><span class="sxs-lookup"><span data-stu-id="dce7e-102">Operations on Request Sets</span></span>
<span data-ttu-id="dce7e-103">设置 Oracle E-business Suite 中的请求是一组报表和已组织成各个阶段的并发程序。</span><span class="sxs-lookup"><span data-stu-id="dce7e-103">A request set in Oracle E-Business Suite is a set of reports and concurrent programs that are organized into various stages.</span></span> <span data-ttu-id="dce7e-104">可以使用单个请求设置为运行一组报表和并发程序。</span><span class="sxs-lookup"><span data-stu-id="dce7e-104">You can use a single request set to run a set of reports and concurrent programs.</span></span> <span data-ttu-id="dce7e-105">请求集划分为一个或多个阶段，并且每个阶段包含了一组报表和并发程序。</span><span class="sxs-lookup"><span data-stu-id="dce7e-105">Request sets are divided into one or more stages, and each stage contains a set of reports and concurrent programs.</span></span> <span data-ttu-id="dce7e-106">这些阶段链接，并定义每个阶段的执行顺序。</span><span class="sxs-lookup"><span data-stu-id="dce7e-106">These stages are linked with each other, and the order of the execution of each stage is defined.</span></span> <span data-ttu-id="dce7e-107">有关请求集的多个特定于 Oracle 的信息，请转到[ http://go.microsoft.com/fwlink/p/?LinkId=129539 ](http://go.microsoft.com/fwlink/p/?LinkId=129539)。</span><span class="sxs-lookup"><span data-stu-id="dce7e-107">For more Oracle-specific information about request sets, go to [http://go.microsoft.com/fwlink/p/?LinkId=129539](http://go.microsoft.com/fwlink/p/?LinkId=129539).</span></span>  
  
 [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] <span data-ttu-id="dce7e-108">可以在 Oracle E-business Suite 中执行请求集。</span><span class="sxs-lookup"><span data-stu-id="dce7e-108">enables you to execute request sets in Oracle E-Business Suite.</span></span> <span data-ttu-id="dce7e-109">请求集将作为中的操作公开[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="dce7e-109">The request sets are exposed as operations in the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span> <span data-ttu-id="dce7e-110">请求集包含一组并发程序，因为这些并发程序将是输入的参数，为请求设置操作。</span><span class="sxs-lookup"><span data-stu-id="dce7e-110">Since a request set contains a set of concurrent programs, those concurrent programs are the input parameters for a request set operation.</span></span> <span data-ttu-id="dce7e-111">并发程序，以及请求设置操作采用四个复杂类型参数和简单类型参数作为输入。</span><span class="sxs-lookup"><span data-stu-id="dce7e-111">Along with the concurrent programs, the request set operation takes four complex type parameters and a simple type parameter as input.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="dce7e-112">您必须设置应用程序上下文设置请求[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]才能执行请求集的任何操作。</span><span class="sxs-lookup"><span data-stu-id="dce7e-112">You must set the applications context for request sets in [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] before you can perform any operations on request sets.</span></span> <span data-ttu-id="dce7e-113">这是因为设置应用程序上下文通过设置 （如责任、 组织和语言设置） 的用户首选项和某一项目的访问控制来帮助实现 Oracle E-business Suite 中的安全事务。</span><span class="sxs-lookup"><span data-stu-id="dce7e-113">This is because setting applications context facilitates secure transactions in Oracle E-Business Suite by setting user preferences (such as responsibility, organization, and language settings) and access control for an artifact.</span></span> <span data-ttu-id="dce7e-114">有关应用程序上下文中，以及如何将其设置的信息，请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。</span><span class="sxs-lookup"><span data-stu-id="dce7e-114">For information about applications context, and how to set it, see [Set Application Context](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span></span>  
  
## <a name="complex-type-parameters"></a><span data-ttu-id="dce7e-115">复杂类型参数</span><span class="sxs-lookup"><span data-stu-id="dce7e-115">Complex type parameters</span></span>
  
-   <span data-ttu-id="dce7e-116">**SetRelClassOptions**:可以设置的请求集的计划选项。</span><span class="sxs-lookup"><span data-stu-id="dce7e-116">**SetRelClassOptions**: Enables you to set scheduling options for the request set.</span></span> <span data-ttu-id="dce7e-117">如果设置 SetRelClassOptions 和 SetRepeatOptions SetRelClassOptions 需要优先顺序。</span><span class="sxs-lookup"><span data-stu-id="dce7e-117">If both SetRelClassOptions and SetRepeatOptions are set then SetRelClassOptions will take precedence.</span></span> <span data-ttu-id="dce7e-118">SetRelClassOptions 将作为参数的以下选项：</span><span class="sxs-lookup"><span data-stu-id="dce7e-118">SetRelClassOptions takes the following options as parameters:</span></span>  
  
    -   <span data-ttu-id="dce7e-119">**应用程序**:指示请求集关联的应用程序的短名称。</span><span class="sxs-lookup"><span data-stu-id="dce7e-119">**Application**: Indicates the short name of the application associated with the request set.</span></span>  
  
    -   <span data-ttu-id="dce7e-120">**类名**:指示与请求集相关联的类的名称。</span><span class="sxs-lookup"><span data-stu-id="dce7e-120">**ClassName**: Indicates the name of the class associated with the request set.</span></span>  
  
    -   <span data-ttu-id="dce7e-121">**CanceOrHold**:指示取消或保留标志。</span><span class="sxs-lookup"><span data-stu-id="dce7e-121">**CanceOrHold**: Indicates the Cancel or Hold flag.</span></span>  
  
    -   <span data-ttu-id="dce7e-122">**StaleDate**:表示该日期当天或之后此如果请求集尚未运行，也将取消请求集。</span><span class="sxs-lookup"><span data-stu-id="dce7e-122">**StaleDate**: Indicates the date on or after which this request set will be canceled if the request set has not yet run.</span></span>  
  
    -   <span data-ttu-id="dce7e-123">**ContinueOnFail**:指示请求集提交应继续还是 SetRelClassOptions 失败的情况下引发异常。</span><span class="sxs-lookup"><span data-stu-id="dce7e-123">**ContinueOnFail**: Indicates whether the request set submission should continue or throw an exception in case SetRelClassOptions fails.</span></span> <span data-ttu-id="dce7e-124">您可以指定"True"（继续） 或"False"（引发了异常）。</span><span class="sxs-lookup"><span data-stu-id="dce7e-124">You can specify “True” (continue) or “False” (throw an exception).</span></span>  
  
-   <span data-ttu-id="dce7e-125">**SetPrintOptions**:可以设置的请求集的打印选项。</span><span class="sxs-lookup"><span data-stu-id="dce7e-125">**SetPrintOptions**: Enables you to set the print options for the request set.</span></span> <span data-ttu-id="dce7e-126">SetPrintOptions 将作为参数的以下选项：</span><span class="sxs-lookup"><span data-stu-id="dce7e-126">SetPrintOptions takes the following options as parameters:</span></span>  
  
    -   <span data-ttu-id="dce7e-127">**打印机**:指示应发送请求集输出的位置的打印机名称。</span><span class="sxs-lookup"><span data-stu-id="dce7e-127">**Printer**: Indicates the printer name where the request set output should be sent.</span></span>  
  
    -   <span data-ttu-id="dce7e-128">**样式**:表示用于打印请求集输出的打印样式。</span><span class="sxs-lookup"><span data-stu-id="dce7e-128">**Style**: Indicates the print style used to print the request set output.</span></span> <span data-ttu-id="dce7e-129">例如，可以指定的方向 （"风景"或"纵向"）。</span><span class="sxs-lookup"><span data-stu-id="dce7e-129">For example, you can specify the orientation (“Landscape” or “Portrait”).</span></span>  
  
    -   <span data-ttu-id="dce7e-130">**副本**:指示请求设置输出的打印的份数。</span><span class="sxs-lookup"><span data-stu-id="dce7e-130">**Copies**: Indicates the number of copies to be printed of the request set output.</span></span>  
  
    -   <span data-ttu-id="dce7e-131">**SaveOutput**:指示要保存的输出文件。</span><span class="sxs-lookup"><span data-stu-id="dce7e-131">**SaveOutput**: Indicates whether or not to save the output file.</span></span> <span data-ttu-id="dce7e-132">您可以指定"True"False"。</span><span class="sxs-lookup"><span data-stu-id="dce7e-132">You can specify “True” or “False”.</span></span>  
  
    -   <span data-ttu-id="dce7e-133">**PrintTogether**:仅适用于子请求。</span><span class="sxs-lookup"><span data-stu-id="dce7e-133">**PrintTogether**: Applicable only for sub-requests.</span></span> <span data-ttu-id="dce7e-134">指示如何打印输出的子请求。</span><span class="sxs-lookup"><span data-stu-id="dce7e-134">Indicates how the output of sub-requests is printed.</span></span> <span data-ttu-id="dce7e-135">如果指定"Y"，在所有子请求都完成后才打印输出的子请求。</span><span class="sxs-lookup"><span data-stu-id="dce7e-135">If you specify “Y”, the output of sub-requests is printed only after all the sub-requests are complete.</span></span> <span data-ttu-id="dce7e-136">如果指定"N"，每个子请求的输出打印在它完成。</span><span class="sxs-lookup"><span data-stu-id="dce7e-136">If you specify “N”, the output of each sub-request is printed as it completes.</span></span>  
  
    -   <span data-ttu-id="dce7e-137">**ContinueOnFail**:指示请求集提交应继续还是 SetPrintOptions 失败的情况下引发异常。</span><span class="sxs-lookup"><span data-stu-id="dce7e-137">**ContinueOnFail**: Indicates whether the request set submission should continue or throw an exception in case SetPrintOptions fails.</span></span> <span data-ttu-id="dce7e-138">您可以指定"True"（继续） 或"False"（引发了异常）。</span><span class="sxs-lookup"><span data-stu-id="dce7e-138">You can specify “True” (continue) or “False” (throw an exception).</span></span>  
  
-   <span data-ttu-id="dce7e-139">**SetRepeatOptions**:使您可以设置的请求集重复的选项。</span><span class="sxs-lookup"><span data-stu-id="dce7e-139">**SetRepeatOptions**: Enables you to set the repeat options for the request set.</span></span> <span data-ttu-id="dce7e-140">SetRepeatOptions 将作为参数的以下选项：</span><span class="sxs-lookup"><span data-stu-id="dce7e-140">SetRepeatOptions takes the following options as parameters:</span></span>  
  
    -   <span data-ttu-id="dce7e-141">**RepeatTime**:指示要重复的请求集日期的时间。</span><span class="sxs-lookup"><span data-stu-id="dce7e-141">**RepeatTime**: Indicates the time of day to repeat the request set.</span></span>  
  
    -   <span data-ttu-id="dce7e-142">**RepeatInterval**:此参数是仅在**RepeatTime**为 NULL。</span><span class="sxs-lookup"><span data-stu-id="dce7e-142">**RepeatInterval**: This parameter is applicable only when **RepeatTime** is NULL.</span></span> <span data-ttu-id="dce7e-143">指示请求的重新提交之间的间隔。</span><span class="sxs-lookup"><span data-stu-id="dce7e-143">Indicates the interval between resubmissions of the request.</span></span> <span data-ttu-id="dce7e-144">使用此选项与**RepeatUnit**指定重新提交之间的时间。</span><span class="sxs-lookup"><span data-stu-id="dce7e-144">Use this option along with **RepeatUnit** to specify the time between resubmissions.</span></span>  
  
    -   <span data-ttu-id="dce7e-145">**RepeatUnit**:此参数是仅在**RepeatTime**为 NULL。</span><span class="sxs-lookup"><span data-stu-id="dce7e-145">**RepeatUnit**: This parameter is applicable only when **RepeatTime** is NULL.</span></span> <span data-ttu-id="dce7e-146">与所用的时间单位**RepeatInterval**指定之间重新提交请求的时间。</span><span class="sxs-lookup"><span data-stu-id="dce7e-146">The unit of time used along with **RepeatInterval** to specify the time between resubmissions of the request.</span></span> <span data-ttu-id="dce7e-147">您可以指定"分钟数"、"小时"、"天"或"月"。</span><span class="sxs-lookup"><span data-stu-id="dce7e-147">You can specify “Minutes”, “Hours”, “Days” or “Months”.</span></span>  
  
    -   <span data-ttu-id="dce7e-148">**RepeatType**:此参数是仅在**RepeatTime**为 NULL。</span><span class="sxs-lookup"><span data-stu-id="dce7e-148">**RepeatType**: This parameter is applicable only when **RepeatTime** is NULL.</span></span> <span data-ttu-id="dce7e-149">指示是否将重复间隔应用的上一个请求的"启动"设置执行后或在上一个请求的"end"设置执行。</span><span class="sxs-lookup"><span data-stu-id="dce7e-149">Indicates whether the repeat interval is applied after the “start” of a previous request set execution or after the “end” of a previous request set execution.</span></span>  
  
    -   <span data-ttu-id="dce7e-150">**RepeatEndTime**:指示要停止重新提交请求集的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="dce7e-150">**RepeatEndTime**: Indicates the date and time to stop resubmitting the request set.</span></span>  
  
    -   <span data-ttu-id="dce7e-151">**ContinueOnFail**:指示请求集提交应继续还是 SetRepeatOptions 失败的情况下引发异常。</span><span class="sxs-lookup"><span data-stu-id="dce7e-151">**ContinueOnFail**: Indicates whether the request set submission should continue or throw an exception in case SetRepeatOptions fails.</span></span> <span data-ttu-id="dce7e-152">您可以指定"True"（继续） 或"False"（引发了异常）。</span><span class="sxs-lookup"><span data-stu-id="dce7e-152">You can specify “True” (continue) or “False” (throw an exception).</span></span>  
  
-   <span data-ttu-id="dce7e-153">**SetNlsOptions**:可以设置的请求集的 NLS 选项。</span><span class="sxs-lookup"><span data-stu-id="dce7e-153">**SetNlsOptions**: Enables you to set the NLS options for the request set.</span></span> <span data-ttu-id="dce7e-154">SetNlsOptions 将作为参数的以下选项：</span><span class="sxs-lookup"><span data-stu-id="dce7e-154">SetNlsOptions takes the following options as parameters:</span></span>  
  
    -   <span data-ttu-id="dce7e-155">**语言**:指示 NLS 语言。</span><span class="sxs-lookup"><span data-stu-id="dce7e-155">**Language**: Indicates the NLS language.</span></span>  
  
    -   <span data-ttu-id="dce7e-156">**语言**:指示语言区域。</span><span class="sxs-lookup"><span data-stu-id="dce7e-156">**Language**: Indicates the language territory.</span></span>  
  
    -   <span data-ttu-id="dce7e-157">**ContinueOnFail**:指示请求集提交应继续还是 SetNlsOptions 失败的情况下引发异常。</span><span class="sxs-lookup"><span data-stu-id="dce7e-157">**ContinueOnFail**: Indicates whether the request set submission should continue or throw an exception in case SetNlsOptions fails.</span></span> <span data-ttu-id="dce7e-158">您可以指定"True"（继续） 或"False"（引发了异常）。</span><span class="sxs-lookup"><span data-stu-id="dce7e-158">You can specify “True” (continue) or “False” (throw an exception).</span></span>  
  
## <a name="simple-type-parameter"></a><span data-ttu-id="dce7e-159">简单类型参数</span><span class="sxs-lookup"><span data-stu-id="dce7e-159">Simple type parameter</span></span>
  
 <span data-ttu-id="dce7e-160">**startTime**:指示请求集应开始运行的时间。</span><span class="sxs-lookup"><span data-stu-id="dce7e-160">**StartTime**: Indicates the time at which the request set should start running.</span></span>  
  
 <span data-ttu-id="dce7e-161">如果请求设置成功完成，返回的 ID 的并发请求。</span><span class="sxs-lookup"><span data-stu-id="dce7e-161">If the request set completes successfully, a concurrent request ID is returned.</span></span> <span data-ttu-id="dce7e-162">否则，返回"0"。</span><span class="sxs-lookup"><span data-stu-id="dce7e-162">Otherwise, “0” is returned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dce7e-163">请参阅</span><span class="sxs-lookup"><span data-stu-id="dce7e-163">See Also</span></span>  
 <span data-ttu-id="dce7e-164">[哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="dce7e-164">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span></span>