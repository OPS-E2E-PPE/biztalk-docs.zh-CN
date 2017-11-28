---
title: "对请求设置的操作 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0537354d-821e-4cf9-a4d1-f4e7d1643df9
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8051a94df28df4090f78287070c5143e6f866ed7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="operations-on-request-sets"></a><span data-ttu-id="9ca40-102">对请求设置的操作</span><span class="sxs-lookup"><span data-stu-id="9ca40-102">Operations on Request Sets</span></span>
<span data-ttu-id="9ca40-103">在 Oracle E-business Suite 中设置的请求是一组报表和组织成各个阶段的并发程序。</span><span class="sxs-lookup"><span data-stu-id="9ca40-103">A request set in Oracle E-Business Suite is a set of reports and concurrent programs that are organized into various stages.</span></span> <span data-ttu-id="9ca40-104">你可以使用单个请求设置为运行一组报表和并发程序。</span><span class="sxs-lookup"><span data-stu-id="9ca40-104">You can use a single request set to run a set of reports and concurrent programs.</span></span> <span data-ttu-id="9ca40-105">请求集划分为一个或多个阶段和每个阶段包含一组报表和并发程序。</span><span class="sxs-lookup"><span data-stu-id="9ca40-105">Request sets are divided into one or more stages, and each stage contains a set of reports and concurrent programs.</span></span> <span data-ttu-id="9ca40-106">这些阶段链接相互，且每个阶段执行的顺序进行定义。</span><span class="sxs-lookup"><span data-stu-id="9ca40-106">These stages are linked with each other, and the order of the execution of each stage is defined.</span></span> <span data-ttu-id="9ca40-107">有关请求集的多个特定于 Oracle 的信息，请转到[http://go.microsoft.com/fwlink/p/?LinkId=129539](http://go.microsoft.com/fwlink/p/?LinkId=129539)。</span><span class="sxs-lookup"><span data-stu-id="9ca40-107">For more Oracle-specific information about request sets, go to [http://go.microsoft.com/fwlink/p/?LinkId=129539](http://go.microsoft.com/fwlink/p/?LinkId=129539).</span></span>  
  
 [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]<span data-ttu-id="9ca40-108">使您能够在 Oracle E-business Suite 中执行请求集。</span><span class="sxs-lookup"><span data-stu-id="9ca40-108"> enables you to execute request sets in Oracle E-Business Suite.</span></span> <span data-ttu-id="9ca40-109">中的操作作为公开请求集[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="9ca40-109">The request sets are exposed as operations in the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span> <span data-ttu-id="9ca40-110">由于请求集包含的并发程序集时，这些并发的程序的输入的参数为请求设置操作。</span><span class="sxs-lookup"><span data-stu-id="9ca40-110">Since a request set contains a set of concurrent programs, those concurrent programs are the input parameters for a request set operation.</span></span> <span data-ttu-id="9ca40-111">并发的程序，以及请求设置操作可使用四个复杂类型参数和简单类型参数作为输入。</span><span class="sxs-lookup"><span data-stu-id="9ca40-111">Along with the concurrent programs, the request set operation takes four complex type parameters and a simple type parameter as input.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9ca40-112">为请求设置中，必须设置应用程序上下文[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]可以执行对请求设置的任何操作之前。</span><span class="sxs-lookup"><span data-stu-id="9ca40-112">You must set the applications context for request sets in [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] before you can perform any operations on request sets.</span></span> <span data-ttu-id="9ca40-113">这是因为设置应用程序上下文通过 Oracle E-business Suite 中的安全事务来促进设置 （例如责任、 组织和语言设置） 的用户首选项和项目的访问控制。</span><span class="sxs-lookup"><span data-stu-id="9ca40-113">This is because setting applications context facilitates secure transactions in Oracle E-Business Suite by setting user preferences (such as responsibility, organization, and language settings) and access control for an artifact.</span></span> <span data-ttu-id="9ca40-114">有关应用程序上下文中，以及如何将其设置的信息，请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。</span><span class="sxs-lookup"><span data-stu-id="9ca40-114">For information about applications context, and how to set it, see [Set Application Context](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span></span>  
  
## <a name="complex-type-parameters"></a><span data-ttu-id="9ca40-115">复杂类型参数</span><span class="sxs-lookup"><span data-stu-id="9ca40-115">Complex type parameters</span></span>
  
-   <span data-ttu-id="9ca40-116">**SetRelClassOptions**： 使你能够设置请求组的计划选项。</span><span class="sxs-lookup"><span data-stu-id="9ca40-116">**SetRelClassOptions**: Enables you to set scheduling options for the request set.</span></span> <span data-ttu-id="9ca40-117">如果设置 SetRelClassOptions 和 SetRepeatOptions SetRelClassOptions 将取得优先权。</span><span class="sxs-lookup"><span data-stu-id="9ca40-117">If both SetRelClassOptions and SetRepeatOptions are set then SetRelClassOptions will take precedence.</span></span> <span data-ttu-id="9ca40-118">SetRelClassOptions 使用作为参数的以下选项：</span><span class="sxs-lookup"><span data-stu-id="9ca40-118">SetRelClassOptions takes the following options as parameters:</span></span>  
  
    -   <span data-ttu-id="9ca40-119">**应用程序**： 指示请求集关联的应用程序的短名称。</span><span class="sxs-lookup"><span data-stu-id="9ca40-119">**Application**: Indicates the short name of the application associated with the request set.</span></span>  
  
    -   <span data-ttu-id="9ca40-120">**类名**： 指示请求集与关联的类的名称。</span><span class="sxs-lookup"><span data-stu-id="9ca40-120">**ClassName**: Indicates the name of the class associated with the request set.</span></span>  
  
    -   <span data-ttu-id="9ca40-121">**CanceOrHold**： 指示取消或保留标志。</span><span class="sxs-lookup"><span data-stu-id="9ca40-121">**CanceOrHold**: Indicates the Cancel or Hold flag.</span></span>  
  
    -   <span data-ttu-id="9ca40-122">**StaleDate**： 指示日期或之后此如果请求集尚未运行，将被取消请求组。</span><span class="sxs-lookup"><span data-stu-id="9ca40-122">**StaleDate**: Indicates the date on or after which this request set will be canceled if the request set has not yet run.</span></span>  
  
    -   <span data-ttu-id="9ca40-123">**ContinueOnFail**： 指示请求集提交是否应继续还是 SetRelClassOptions 失败的情况下引发异常。</span><span class="sxs-lookup"><span data-stu-id="9ca40-123">**ContinueOnFail**: Indicates whether the request set submission should continue or throw an exception in case SetRelClassOptions fails.</span></span> <span data-ttu-id="9ca40-124">你可以指定"True"（继续） 或"False"（引发了异常）。</span><span class="sxs-lookup"><span data-stu-id="9ca40-124">You can specify “True” (continue) or “False” (throw an exception).</span></span>  
  
-   <span data-ttu-id="9ca40-125">**SetPrintOptions**： 使你能够设置请求集的打印选项。</span><span class="sxs-lookup"><span data-stu-id="9ca40-125">**SetPrintOptions**: Enables you to set the print options for the request set.</span></span> <span data-ttu-id="9ca40-126">SetPrintOptions 使用作为参数的以下选项：</span><span class="sxs-lookup"><span data-stu-id="9ca40-126">SetPrintOptions takes the following options as parameters:</span></span>  
  
    -   <span data-ttu-id="9ca40-127">**打印机**： 指示应将设置输出该申请发送其中的打印机名称。</span><span class="sxs-lookup"><span data-stu-id="9ca40-127">**Printer**: Indicates the printer name where the request set output should be sent.</span></span>  
  
    -   <span data-ttu-id="9ca40-128">**样式**： 指示用于打印请求集输出的打印样式。</span><span class="sxs-lookup"><span data-stu-id="9ca40-128">**Style**: Indicates the print style used to print the request set output.</span></span> <span data-ttu-id="9ca40-129">例如，你可以指定的方向 （"横向"或"纵向"）。</span><span class="sxs-lookup"><span data-stu-id="9ca40-129">For example, you can specify the orientation (“Landscape” or “Portrait”).</span></span>  
  
    -   <span data-ttu-id="9ca40-130">**副本**： 指示要打印的请求集输出的副本数。</span><span class="sxs-lookup"><span data-stu-id="9ca40-130">**Copies**: Indicates the number of copies to be printed of the request set output.</span></span>  
  
    -   <span data-ttu-id="9ca40-131">**SaveOutput**： 指示是否保存输出文件。</span><span class="sxs-lookup"><span data-stu-id="9ca40-131">**SaveOutput**: Indicates whether or not to save the output file.</span></span> <span data-ttu-id="9ca40-132">你可以指定"True"False"。</span><span class="sxs-lookup"><span data-stu-id="9ca40-132">You can specify “True” or “False”.</span></span>  
  
    -   <span data-ttu-id="9ca40-133">**PrintTogether**： 仅适用于子请求。</span><span class="sxs-lookup"><span data-stu-id="9ca40-133">**PrintTogether**: Applicable only for sub-requests.</span></span> <span data-ttu-id="9ca40-134">指示如何打印的子请求输出。</span><span class="sxs-lookup"><span data-stu-id="9ca40-134">Indicates how the output of sub-requests is printed.</span></span> <span data-ttu-id="9ca40-135">如果指定"Y"，在所有子请求都完成后才将打印的子请求输出。</span><span class="sxs-lookup"><span data-stu-id="9ca40-135">If you specify “Y”, the output of sub-requests is printed only after all the sub-requests are complete.</span></span> <span data-ttu-id="9ca40-136">如果指定"N"，每个子请求的输出将打印在完成。</span><span class="sxs-lookup"><span data-stu-id="9ca40-136">If you specify “N”, the output of each sub-request is printed as it completes.</span></span>  
  
    -   <span data-ttu-id="9ca40-137">**ContinueOnFail**： 指示请求集提交是否应继续还是 SetPrintOptions 失败的情况下引发异常。</span><span class="sxs-lookup"><span data-stu-id="9ca40-137">**ContinueOnFail**: Indicates whether the request set submission should continue or throw an exception in case SetPrintOptions fails.</span></span> <span data-ttu-id="9ca40-138">你可以指定"True"（继续） 或"False"（引发了异常）。</span><span class="sxs-lookup"><span data-stu-id="9ca40-138">You can specify “True” (continue) or “False” (throw an exception).</span></span>  
  
-   <span data-ttu-id="9ca40-139">**SetRepeatOptions**： 使你能够设置的重复请求集选项。</span><span class="sxs-lookup"><span data-stu-id="9ca40-139">**SetRepeatOptions**: Enables you to set the repeat options for the request set.</span></span> <span data-ttu-id="9ca40-140">SetRepeatOptions 使用作为参数的以下选项：</span><span class="sxs-lookup"><span data-stu-id="9ca40-140">SetRepeatOptions takes the following options as parameters:</span></span>  
  
    -   <span data-ttu-id="9ca40-141">**RepeatTime**： 表示一天中重复请求集的时间。</span><span class="sxs-lookup"><span data-stu-id="9ca40-141">**RepeatTime**: Indicates the time of day to repeat the request set.</span></span>  
  
    -   <span data-ttu-id="9ca40-142">**RepeatInterval**： 此参数是适用时，才**RepeatTime**为 NULL。</span><span class="sxs-lookup"><span data-stu-id="9ca40-142">**RepeatInterval**: This parameter is applicable only when **RepeatTime** is NULL.</span></span> <span data-ttu-id="9ca40-143">指示重新提交的请求之间的间隔。</span><span class="sxs-lookup"><span data-stu-id="9ca40-143">Indicates the interval between resubmissions of the request.</span></span> <span data-ttu-id="9ca40-144">使用此选项以及**RepeatUnit**指定之间重新提交的时间。</span><span class="sxs-lookup"><span data-stu-id="9ca40-144">Use this option along with **RepeatUnit** to specify the time between resubmissions.</span></span>  
  
    -   <span data-ttu-id="9ca40-145">**RepeatUnit**： 此参数是适用时，才**RepeatTime**为 NULL。</span><span class="sxs-lookup"><span data-stu-id="9ca40-145">**RepeatUnit**: This parameter is applicable only when **RepeatTime** is NULL.</span></span> <span data-ttu-id="9ca40-146">连同所用的时间单位**RepeatInterval**指定之间重新提交请求的时间。</span><span class="sxs-lookup"><span data-stu-id="9ca40-146">The unit of time used along with **RepeatInterval** to specify the time between resubmissions of the request.</span></span> <span data-ttu-id="9ca40-147">你可以指定"分钟数"、"Hours"、"Days"或"Months"。</span><span class="sxs-lookup"><span data-stu-id="9ca40-147">You can specify “Minutes”, “Hours”, “Days” or “Months”.</span></span>  
  
    -   <span data-ttu-id="9ca40-148">**RepeatType**： 此参数是适用时，才**RepeatTime**为 NULL。</span><span class="sxs-lookup"><span data-stu-id="9ca40-148">**RepeatType**: This parameter is applicable only when **RepeatTime** is NULL.</span></span> <span data-ttu-id="9ca40-149">指示是否将以前的请求的"开始"设置执行之后，或者在以前的请求的"结束"设置执行应用的重复间隔。</span><span class="sxs-lookup"><span data-stu-id="9ca40-149">Indicates whether the repeat interval is applied after the “start” of a previous request set execution or after the “end” of a previous request set execution.</span></span>  
  
    -   <span data-ttu-id="9ca40-150">**RepeatEndTime**： 指示停止重新提交请求集的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="9ca40-150">**RepeatEndTime**: Indicates the date and time to stop resubmitting the request set.</span></span>  
  
    -   <span data-ttu-id="9ca40-151">**ContinueOnFail**： 指示请求集提交是否应继续还是 SetRepeatOptions 失败的情况下引发异常。</span><span class="sxs-lookup"><span data-stu-id="9ca40-151">**ContinueOnFail**: Indicates whether the request set submission should continue or throw an exception in case SetRepeatOptions fails.</span></span> <span data-ttu-id="9ca40-152">你可以指定"True"（继续） 或"False"（引发了异常）。</span><span class="sxs-lookup"><span data-stu-id="9ca40-152">You can specify “True” (continue) or “False” (throw an exception).</span></span>  
  
-   <span data-ttu-id="9ca40-153">**SetNlsOptions**： 使你能够设置请求集 NLS 选项。</span><span class="sxs-lookup"><span data-stu-id="9ca40-153">**SetNlsOptions**: Enables you to set the NLS options for the request set.</span></span> <span data-ttu-id="9ca40-154">SetNlsOptions 使用作为参数的以下选项：</span><span class="sxs-lookup"><span data-stu-id="9ca40-154">SetNlsOptions takes the following options as parameters:</span></span>  
  
    -   <span data-ttu-id="9ca40-155">**语言**： 指示 NLS 语言。</span><span class="sxs-lookup"><span data-stu-id="9ca40-155">**Language**: Indicates the NLS language.</span></span>  
  
    -   <span data-ttu-id="9ca40-156">**语言**： 指示语言区域。</span><span class="sxs-lookup"><span data-stu-id="9ca40-156">**Language**: Indicates the language territory.</span></span>  
  
    -   <span data-ttu-id="9ca40-157">**ContinueOnFail**： 指示请求集提交是否应继续还是 SetNlsOptions 失败的情况下引发异常。</span><span class="sxs-lookup"><span data-stu-id="9ca40-157">**ContinueOnFail**: Indicates whether the request set submission should continue or throw an exception in case SetNlsOptions fails.</span></span> <span data-ttu-id="9ca40-158">你可以指定"True"（继续） 或"False"（引发了异常）。</span><span class="sxs-lookup"><span data-stu-id="9ca40-158">You can specify “True” (continue) or “False” (throw an exception).</span></span>  
  
## <a name="simple-type-parameter"></a><span data-ttu-id="9ca40-159">简单类型参数</span><span class="sxs-lookup"><span data-stu-id="9ca40-159">Simple type parameter</span></span>
  
 <span data-ttu-id="9ca40-160">**StartTime**： 表示请求集应开始运行的时间。</span><span class="sxs-lookup"><span data-stu-id="9ca40-160">**StartTime**: Indicates the time at which the request set should start running.</span></span>  
  
 <span data-ttu-id="9ca40-161">如果请求设置成功完成，则返回 ID 的并发请求。</span><span class="sxs-lookup"><span data-stu-id="9ca40-161">If the request set completes successfully, a concurrent request ID is returned.</span></span> <span data-ttu-id="9ca40-162">否则，返回"0"。</span><span class="sxs-lookup"><span data-stu-id="9ca40-162">Otherwise, “0” is returned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ca40-163">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9ca40-163">See Also</span></span>  
 <span data-ttu-id="9ca40-164">[哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="9ca40-164">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span></span>