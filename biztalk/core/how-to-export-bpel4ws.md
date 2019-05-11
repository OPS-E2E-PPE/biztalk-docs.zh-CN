---
title: 如何导出 BPEL4WS |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BPEL4WS, exporting
- BPEL4WS, restrictions
- orchestrations, BPEL4WS
ms.assetid: 4648dfcf-cf48-4471-b088-07252c080fb8
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 655c3947283b5cd4cb45d863c416051d08a37a98
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385060"
---
# <a name="how-to-export-bpel4ws"></a><span data-ttu-id="4ae57-102">如何导出 BPEL4WS</span><span class="sxs-lookup"><span data-stu-id="4ae57-102">How to Export BPEL4WS</span></span>
<span data-ttu-id="4ae57-103">可以将现有的 BizTalk 业务流程导出到 BPEL4WS。</span><span class="sxs-lookup"><span data-stu-id="4ae57-103">You can export an existing BizTalk orchestration to BPEL4WS.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4ae57-104">此版本的 BizTalk Server 支持 BPEL4WS 1.1。</span><span class="sxs-lookup"><span data-stu-id="4ae57-104">This release of BizTalk Server supports BPEL4WS 1.1.</span></span> <span data-ttu-id="4ae57-105">无法导入或导出 BPEL4WS 1.0。</span><span class="sxs-lookup"><span data-stu-id="4ae57-105">You cannot import or export BPEL4WS 1.0.</span></span>  
  
 <span data-ttu-id="4ae57-106">如果要导出，bpel4ws 编译需要业务流程包含仅是 XLANG/s 和 BPEL4WS 之间通用的功能或可翻译成 BPEL4WS 中，而不会影响行为的功能。</span><span class="sxs-lookup"><span data-stu-id="4ae57-106">If you are exporting, BPEL4WS compliance for compilation requires that orchestrations contain only features that are common between XLANG/s and BPEL4WS, or features that can be translated into BPEL4WS without affecting behavior.</span></span>  
  
## <a name="export-restrictions-on-orchestrations-for-bpel4ws-compliance"></a><span data-ttu-id="4ae57-107">导出的业务流程的 bpel4ws 的限制</span><span class="sxs-lookup"><span data-stu-id="4ae57-107">Export restrictions on orchestrations for BPEL4WS compliance</span></span>  
  
-   <span data-ttu-id="4ae57-108">不能使用调用业务流程形状或启动业务流程形状。</span><span class="sxs-lookup"><span data-stu-id="4ae57-108">You cannot use the Call Orchestration shape or the Start Orchestration shape.</span></span>  
  
-   <span data-ttu-id="4ae57-109">不能使用转换形状。</span><span class="sxs-lookup"><span data-stu-id="4ae57-109">You cannot use the Transform shape.</span></span>  
  
-   <span data-ttu-id="4ae57-110">不能调用自定义.NET 组件上的方法。</span><span class="sxs-lookup"><span data-stu-id="4ae57-110">You cannot invoke methods on custom .NET components.</span></span>  
  
-   <span data-ttu-id="4ae57-111">不能对一个长时间运行的事务应用超时。</span><span class="sxs-lookup"><span data-stu-id="4ae57-111">You cannot apply a timeout to a long-running transaction.</span></span>  
  
-   <span data-ttu-id="4ae57-112">您的业务流程不能采用参数。</span><span class="sxs-lookup"><span data-stu-id="4ae57-112">Your orchestration cannot take parameters.</span></span>  
  
-   <span data-ttu-id="4ae57-113">可调用补偿处理程序不能有参数。</span><span class="sxs-lookup"><span data-stu-id="4ae57-113">Callable compensation handlers cannot have parameters.</span></span>  
  
-   <span data-ttu-id="4ae57-114">变量类型必须是在 XPATH 中受支持。</span><span class="sxs-lookup"><span data-stu-id="4ae57-114">Variable types must be supportable in XPATH.</span></span>  
  
-   <span data-ttu-id="4ae57-115">不能使用挂起形状。</span><span class="sxs-lookup"><span data-stu-id="4ae57-115">You cannot use the Suspend shape.</span></span>  
  
-   <span data-ttu-id="4ae57-116">文本值必须是以下类型之一：</span><span class="sxs-lookup"><span data-stu-id="4ae57-116">Literal values must be one of the following types:</span></span>  
  
     <span data-ttu-id="4ae57-117">布尔值、 char、 byte、 sbyte、 int32、 uint32、 int64、 uint64、 single、 double、 字符串</span><span class="sxs-lookup"><span data-stu-id="4ae57-117">boolean, char, byte, sbyte, int32, uint32, int64, uint64, single, double, string</span></span>  
  
-   <span data-ttu-id="4ae57-118">仅在以下数字类型的操作数上不允许算术运算符：</span><span class="sxs-lookup"><span data-stu-id="4ae57-118">Arithmetic operators are allowed only on operands of following numeric types:</span></span>  
  
     <span data-ttu-id="4ae57-119">byte、 sbyte、 int32、 uint32、 int64、 uint64、 single、 double</span><span class="sxs-lookup"><span data-stu-id="4ae57-119">byte, sbyte, int32, uint32, int64, uint64, single, double</span></span>  
  
-   <span data-ttu-id="4ae57-120">关系运算符不能应用于类型 char。</span><span class="sxs-lookup"><span data-stu-id="4ae57-120">Relational operators cannot be applied to type char.</span></span>  
  
-   <span data-ttu-id="4ae57-121">在表达式中不能对 servicelink 属性的引用。</span><span class="sxs-lookup"><span data-stu-id="4ae57-121">You cannot make a reference to a servicelink property in an expression.</span></span>  
  
-   <span data-ttu-id="4ae57-122">你不能执行任何操作之间**发送**形状和一个**接收**使用相同的出站请求-响应端口的形状。</span><span class="sxs-lookup"><span data-stu-id="4ae57-122">You cannot perform any actions between a **Send** shape and a **Receive** shape that use the same outbound request-response port.</span></span>  
  
-   <span data-ttu-id="4ae57-123">不能间接引用 web 服务，如通过对另一个项目的引用，其中包含一个引用。</span><span class="sxs-lookup"><span data-stu-id="4ae57-123">You cannot indirectly reference a web service, as through a reference to another project that contains a reference.</span></span> <span data-ttu-id="4ae57-124">在项目中，必须显式引用 web 服务。</span><span class="sxs-lookup"><span data-stu-id="4ae57-124">You must explicitly reference the web service in your project.</span></span>  
  
-   <span data-ttu-id="4ae57-125">不能在延迟中指定常数 DateTime 或 TimeSpan。</span><span class="sxs-lookup"><span data-stu-id="4ae57-125">You cannot specify a constant DateTime or TimeSpan in a delay.</span></span> <span data-ttu-id="4ae57-126">而是在 System.Xml 命名空间中使用转换类之一：</span><span class="sxs-lookup"><span data-stu-id="4ae57-126">Instead, use one of the conversion classes in the System.Xml namespace:</span></span>  
  
     <span data-ttu-id="4ae57-127">对于常数 DateTime:System.Xml.XmlConvert.ToDateTime, e.g System.Xml.XmlConvert.ToDateTime("2004-04-15")</span><span class="sxs-lookup"><span data-stu-id="4ae57-127">For a constant DateTime: System.Xml.XmlConvert.ToDateTime, e.g System.Xml.XmlConvert.ToDateTime("2004-04-15")</span></span>  
  
     <span data-ttu-id="4ae57-128">对于常数 TimeSpan:System.Xml.XmlConvert.ToTimeSpan, e.g System.Xml.XmlConvert.ToTimeSpan("2004-04-15")</span><span class="sxs-lookup"><span data-stu-id="4ae57-128">For a constant TimeSpan: System.Xml.XmlConvert.ToTimeSpan, e.g System.Xml.XmlConvert.ToTimeSpan("2004-04-15")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4ae57-129">字符文本导出为无符号整数。</span><span class="sxs-lookup"><span data-stu-id="4ae57-129">Character literals are exported as unsigned integers.</span></span> <span data-ttu-id="4ae57-130">例如，a 导出为 97，b 导出为 98，等等。</span><span class="sxs-lookup"><span data-stu-id="4ae57-130">For example, 'a' is exported as 97, 'b' is exported as 98, and so forth.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="4ae57-131">标识符名称必须符合 W3C 可扩展标记语言 (XML) 1.0 规范。</span><span class="sxs-lookup"><span data-stu-id="4ae57-131">Identifier names must conform to the W3C Extensible Markup Language (XML) 1.0 specification.</span></span>  
  
#### <a name="to-export-an-orchestration-to-bpel4ws"></a><span data-ttu-id="4ae57-132">若要将业务流程导出到 BPEL4WS</span><span class="sxs-lookup"><span data-stu-id="4ae57-132">To export an orchestration to BPEL4WS</span></span>  
  
1.  <span data-ttu-id="4ae57-133">将 BizTalk 业务流程类型的新项添加到你的项目。</span><span class="sxs-lookup"><span data-stu-id="4ae57-133">Add a new item of type BizTalk Orchestration to your project.</span></span>  
  
2.  <span data-ttu-id="4ae57-134">单击设计图面以显示业务流程属性窗口。</span><span class="sxs-lookup"><span data-stu-id="4ae57-134">Click the design surface to bring up the Orchestration Properties window.</span></span>  
  
3.  <span data-ttu-id="4ae57-135">设置**模块可导出**为 True。</span><span class="sxs-lookup"><span data-stu-id="4ae57-135">Set **Module Exportable** to True.</span></span>  
  
4.  <span data-ttu-id="4ae57-136">所需的命名空间中的类型**模块 XML 目标 Namespace**。</span><span class="sxs-lookup"><span data-stu-id="4ae57-136">Type in the namespace you want for **Module XML Target Namespace**.</span></span>  
  
5.  <span data-ttu-id="4ae57-137">设置**业务流程可导出**为 True。</span><span class="sxs-lookup"><span data-stu-id="4ae57-137">Set **Orchestration Exportable** to True.</span></span>  
  
6.  <span data-ttu-id="4ae57-138">所需的命名空间中的类型**业务流程 XML 目标 Namespace**。</span><span class="sxs-lookup"><span data-stu-id="4ae57-138">Type in the namespace you want for **Orchestration XML Target Namespace**.</span></span>  
  
7.  <span data-ttu-id="4ae57-139">在解决方案资源管理器中右键单击。您的业务流程的 ODX 文件。</span><span class="sxs-lookup"><span data-stu-id="4ae57-139">In Solution Explorer, right-click the .ODX file for your orchestration.</span></span>  
  
8.  <span data-ttu-id="4ae57-140">选择**导出到 BPEL**。</span><span class="sxs-lookup"><span data-stu-id="4ae57-140">Select **Export to BPEL**.</span></span>  
  
     <span data-ttu-id="4ae57-141">您的业务流程将导出到 BPEL4WS。</span><span class="sxs-lookup"><span data-stu-id="4ae57-141">Your orchestration will be exported to BPEL4WS.</span></span> <span data-ttu-id="4ae57-142">请参阅输出窗口和任务列表以确认成功或诊断问题。</span><span class="sxs-lookup"><span data-stu-id="4ae57-142">See the Output Window and Task List to confirm success or diagnose problems.</span></span> <span data-ttu-id="4ae57-143">导出成功后,。WSDL 文件和一个。将你的项目目录中创建 BPEL 文件。</span><span class="sxs-lookup"><span data-stu-id="4ae57-143">Once your export succeeds, a .WSDL file and a .BPEL file will be created in your project directory.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4ae57-144">如果您的业务流程包含角色链接 （服务链接） 赋值或动态端口的文本赋值，BizTalk 将生成虚拟 BPEL4WS 终结点引用，并将引发警告。</span><span class="sxs-lookup"><span data-stu-id="4ae57-144">If your orchestration contains an assignment to a role link (service link) or a literal assignment to a dynamic port, BizTalk generates a dummy BPEL4WS endpoint reference and raises a warning.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ae57-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="4ae57-145">See Also</span></span>  
 <span data-ttu-id="4ae57-146">[如何导入 BPEL4WS](../core/how-to-import-bpel4ws.md) </span><span class="sxs-lookup"><span data-stu-id="4ae57-146">[How to Import BPEL4WS](../core/how-to-import-bpel4ws.md) </span></span>  
 [<span data-ttu-id="4ae57-147">XLANG-s 到 BPEL4WS 的类型转换</span><span class="sxs-lookup"><span data-stu-id="4ae57-147">XLANG-s to BPEL4WS Type Conversions</span></span>](../core/xlang-s-to-bpel4ws-type-conversions.md)