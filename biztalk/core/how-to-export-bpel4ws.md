---
title: "如何导出 BPEL4WS |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BPEL4WS, exporting
- BPEL4WS, restrictions
- orchestrations, BPEL4WS
ms.assetid: 4648dfcf-cf48-4471-b088-07252c080fb8
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b16c2e34b498a9fb8d5fd3f6e69f022c2876a763
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-export-bpel4ws"></a><span data-ttu-id="e6347-102">如何导出 BPEL4WS</span><span class="sxs-lookup"><span data-stu-id="e6347-102">How to Export BPEL4WS</span></span>
<span data-ttu-id="e6347-103">可以将现有的 BizTalk 业务流程导出到 BPEL4WS。</span><span class="sxs-lookup"><span data-stu-id="e6347-103">You can export an existing BizTalk orchestration to BPEL4WS.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e6347-104">此版本的 BizTalk Server 支持 BPEL4WS 1.1。</span><span class="sxs-lookup"><span data-stu-id="e6347-104">This release of BizTalk Server supports BPEL4WS 1.1.</span></span> <span data-ttu-id="e6347-105">无法导入或导出 BPEL4WS 1.0。</span><span class="sxs-lookup"><span data-stu-id="e6347-105">You cannot import or export BPEL4WS 1.0.</span></span>  
  
 <span data-ttu-id="e6347-106">如果要导出，BPEL4WS 编译规范要求业务流程仅包含在 XLANG/s 和 BPEL4WS 之间通用的功能或者在不影响操作的情况下可翻译成 BPEL4WS 的功能。</span><span class="sxs-lookup"><span data-stu-id="e6347-106">If you are exporting, BPEL4WS compliance for compilation requires that orchestrations contain only features that are common between XLANG/s and BPEL4WS, or features that can be translated into BPEL4WS without affecting behavior.</span></span>  
  
## <a name="export-restrictions-on-orchestrations-for-bpel4ws-compliance"></a><span data-ttu-id="e6347-107">对符合 BPEL4WS 规范的业务流程的导出限制</span><span class="sxs-lookup"><span data-stu-id="e6347-107">Export restrictions on orchestrations for BPEL4WS compliance</span></span>  
  
-   <span data-ttu-id="e6347-108">不能使用调用业务流程形状或启动业务流程形状。</span><span class="sxs-lookup"><span data-stu-id="e6347-108">You cannot use the Call Orchestration shape or the Start Orchestration shape.</span></span>  
  
-   <span data-ttu-id="e6347-109">不能使用转换形状。</span><span class="sxs-lookup"><span data-stu-id="e6347-109">You cannot use the Transform shape.</span></span>  
  
-   <span data-ttu-id="e6347-110">不能调用自定义 .NET 组件的方法。</span><span class="sxs-lookup"><span data-stu-id="e6347-110">You cannot invoke methods on custom .NET components.</span></span>  
  
-   <span data-ttu-id="e6347-111">不能对长期事务应用超时。</span><span class="sxs-lookup"><span data-stu-id="e6347-111">You cannot apply a timeout to a long-running transaction.</span></span>  
  
-   <span data-ttu-id="e6347-112">业务流程不能采用参数。</span><span class="sxs-lookup"><span data-stu-id="e6347-112">Your orchestration cannot take parameters.</span></span>  
  
-   <span data-ttu-id="e6347-113">可调用补偿处理程序不能具有参数。</span><span class="sxs-lookup"><span data-stu-id="e6347-113">Callable compensation handlers cannot have parameters.</span></span>  
  
-   <span data-ttu-id="e6347-114">变量类型在 XPATH 中必须是受支持的。</span><span class="sxs-lookup"><span data-stu-id="e6347-114">Variable types must be supportable in XPATH.</span></span>  
  
-   <span data-ttu-id="e6347-115">不能使用挂起形状。</span><span class="sxs-lookup"><span data-stu-id="e6347-115">You cannot use the Suspend shape.</span></span>  
  
-   <span data-ttu-id="e6347-116">文本值必须是以下类型之一：</span><span class="sxs-lookup"><span data-stu-id="e6347-116">Literal values must be one of the following types:</span></span>  
  
     <span data-ttu-id="e6347-117">boolean、char、byte、sbyte、int32、uint32、int64、uint64、single、double、string</span><span class="sxs-lookup"><span data-stu-id="e6347-117">boolean, char, byte, sbyte, int32, uint32, int64, uint64, single, double, string</span></span>  
  
-   <span data-ttu-id="e6347-118">算术运算符只允许用于以下数字类型的操作数：</span><span class="sxs-lookup"><span data-stu-id="e6347-118">Arithmetic operators are allowed only on operands of following numeric types:</span></span>  
  
     <span data-ttu-id="e6347-119">byte、sbyte、int32、uint32、int64、uint64、single、double</span><span class="sxs-lookup"><span data-stu-id="e6347-119">byte, sbyte, int32, uint32, int64, uint64, single, double</span></span>  
  
-   <span data-ttu-id="e6347-120">关系运算符不能应用于 char 类型。</span><span class="sxs-lookup"><span data-stu-id="e6347-120">Relational operators cannot be applied to type char.</span></span>  
  
-   <span data-ttu-id="e6347-121">不能引用表达式中的 servicelink 属性。</span><span class="sxs-lookup"><span data-stu-id="e6347-121">You cannot make a reference to a servicelink property in an expression.</span></span>  
  
-   <span data-ttu-id="e6347-122">你无法执行任何操作之间**发送**形状和**接收**使用相同的出站请求-响应端口的形状。</span><span class="sxs-lookup"><span data-stu-id="e6347-122">You cannot perform any actions between a **Send** shape and a **Receive** shape that use the same outbound request-response port.</span></span>  
  
-   <span data-ttu-id="e6347-123">不能间接引用 Web Services，例如引用包含引用的其他项目。</span><span class="sxs-lookup"><span data-stu-id="e6347-123">You cannot indirectly reference a web service, as through a reference to another project that contains a reference.</span></span> <span data-ttu-id="e6347-124">必须在项目中显式引用 Web Services。</span><span class="sxs-lookup"><span data-stu-id="e6347-124">You must explicitly reference the web service in your project.</span></span>  
  
-   <span data-ttu-id="e6347-125">不能在延迟中指定常数 DateTime 或 TimeSpan。</span><span class="sxs-lookup"><span data-stu-id="e6347-125">You cannot specify a constant DateTime or TimeSpan in a delay.</span></span> <span data-ttu-id="e6347-126">而是在 System.Xml 命名空间中使用以下转换类之一：</span><span class="sxs-lookup"><span data-stu-id="e6347-126">Instead, use one of the conversion classes in the System.Xml namespace:</span></span>  
  
     <span data-ttu-id="e6347-127">对于常数 DateTime，使用 System.Xml.XmlConvert.ToDateTime，例如 System.Xml.XmlConvert.ToDateTime("2004-04-15")</span><span class="sxs-lookup"><span data-stu-id="e6347-127">For a constant DateTime: System.Xml.XmlConvert.ToDateTime, e.g System.Xml.XmlConvert.ToDateTime("2004-04-15")</span></span>  
  
     <span data-ttu-id="e6347-128">对于常数 TimeSpan，使用 System.Xml.XmlConvert.ToTimeSpan，例如 System.Xml.XmlConvert.ToTimeSpan("2004-04-15")</span><span class="sxs-lookup"><span data-stu-id="e6347-128">For a constant TimeSpan: System.Xml.XmlConvert.ToTimeSpan, e.g System.Xml.XmlConvert.ToTimeSpan("2004-04-15")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e6347-129">字符文本导出为无符号整数。</span><span class="sxs-lookup"><span data-stu-id="e6347-129">Character literals are exported as unsigned integers.</span></span> <span data-ttu-id="e6347-130">例如，“a”导出为 97，“b”导出为 98，以此类推。</span><span class="sxs-lookup"><span data-stu-id="e6347-130">For example, 'a' is exported as 97, 'b' is exported as 98, and so forth.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="e6347-131">标识符名称必须符合 W3C 可扩展标记语言 (XML) 1.0 规范。</span><span class="sxs-lookup"><span data-stu-id="e6347-131">Identifier names must conform to the W3C Extensible Markup Language (XML) 1.0 specification.</span></span>  
  
#### <a name="to-export-an-orchestration-to-bpel4ws"></a><span data-ttu-id="e6347-132">将业务流程导出到 BPEL4WS</span><span class="sxs-lookup"><span data-stu-id="e6347-132">To export an orchestration to BPEL4WS</span></span>  
  
1.  <span data-ttu-id="e6347-133">将类型为 BizTalk 业务流程的新项添加到项目中。</span><span class="sxs-lookup"><span data-stu-id="e6347-133">Add a new item of type BizTalk Orchestration to your project.</span></span>  
  
2.  <span data-ttu-id="e6347-134">单击设计图面以打开“业务流程属性”窗口。</span><span class="sxs-lookup"><span data-stu-id="e6347-134">Click the design surface to bring up the Orchestration Properties window.</span></span>  
  
3.  <span data-ttu-id="e6347-135">设置**模块可导出**为 True。</span><span class="sxs-lookup"><span data-stu-id="e6347-135">Set **Module Exportable** to True.</span></span>  
  
4.  <span data-ttu-id="e6347-136">要用于命名空间中的类型**模块 XML 目标 Namespace**。</span><span class="sxs-lookup"><span data-stu-id="e6347-136">Type in the namespace you want for **Module XML Target Namespace**.</span></span>  
  
5.  <span data-ttu-id="e6347-137">设置**业务流程可导出**为 True。</span><span class="sxs-lookup"><span data-stu-id="e6347-137">Set **Orchestration Exportable** to True.</span></span>  
  
6.  <span data-ttu-id="e6347-138">要用于命名空间中的类型**Orchestration XML 目标 Namespace**。</span><span class="sxs-lookup"><span data-stu-id="e6347-138">Type in the namespace you want for **Orchestration XML Target Namespace**.</span></span>  
  
7.  <span data-ttu-id="e6347-139">在解决方案资源管理器，右键单击。您的业务流程的 ODX 文件。</span><span class="sxs-lookup"><span data-stu-id="e6347-139">In Solution Explorer, right-click the .ODX file for your orchestration.</span></span>  
  
8.  <span data-ttu-id="e6347-140">选择**将导出到 BPEL**。</span><span class="sxs-lookup"><span data-stu-id="e6347-140">Select **Export to BPEL**.</span></span>  
  
     <span data-ttu-id="e6347-141">业务流程将导出到 BPEL4WS。</span><span class="sxs-lookup"><span data-stu-id="e6347-141">Your orchestration will be exported to BPEL4WS.</span></span> <span data-ttu-id="e6347-142">查看“输出”窗口和“任务列表”以确认是否成功或诊断问题。</span><span class="sxs-lookup"><span data-stu-id="e6347-142">See the Output Window and Task List to confirm success or diagnose problems.</span></span> <span data-ttu-id="e6347-143">导出成功后，将在项目目录中创建 .WSDL 文件和 .BPEL 文件。</span><span class="sxs-lookup"><span data-stu-id="e6347-143">Once your export succeeds, a .WSDL file and a .BPEL file will be created in your project directory.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e6347-144">如果业务流程包含角色链接（服务链接）的赋值或动态端口的文本赋值，BizTalk 将生成虚拟 BPEL4WS 终结点引用并发出警告。</span><span class="sxs-lookup"><span data-stu-id="e6347-144">If your orchestration contains an assignment to a role link (service link) or a literal assignment to a dynamic port, BizTalk generates a dummy BPEL4WS endpoint reference and raises a warning.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6347-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e6347-145">See Also</span></span>  
 <span data-ttu-id="e6347-146">[如何导入 BPEL4WS](../core/how-to-import-bpel4ws.md) </span><span class="sxs-lookup"><span data-stu-id="e6347-146">[How to Import BPEL4WS](../core/how-to-import-bpel4ws.md) </span></span>  
 [<span data-ttu-id="e6347-147">XLANG-s 的 BPEL4WS 类型转换</span><span class="sxs-lookup"><span data-stu-id="e6347-147">XLANG-s to BPEL4WS Type Conversions</span></span>](../core/xlang-s-to-bpel4ws-type-conversions.md)