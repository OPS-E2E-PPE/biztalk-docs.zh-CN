---
title: "业务流程变量类型 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: orchestrations, variables
ms.assetid: 34990be2-35b6-40ec-b107-42a1c7b45aca
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f388cf112a84d1e6ace00d3930cd6d815d728d89
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="orchestration-variable-types"></a><span data-ttu-id="106f6-102">业务流程变量类型</span><span class="sxs-lookup"><span data-stu-id="106f6-102">Orchestration Variable Types</span></span>
<span data-ttu-id="106f6-103">您可以声明以下预定义类型的变量：</span><span class="sxs-lookup"><span data-stu-id="106f6-103">You can declare variables of the following predefined types:</span></span>  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="106f6-104">boolean</span><span class="sxs-lookup"><span data-stu-id="106f6-104">boolean</span></span>|<span data-ttu-id="106f6-105">byte</span><span class="sxs-lookup"><span data-stu-id="106f6-105">byte</span></span>|<span data-ttu-id="106f6-106">char</span><span class="sxs-lookup"><span data-stu-id="106f6-106">char</span></span>|<span data-ttu-id="106f6-107">datetime</span><span class="sxs-lookup"><span data-stu-id="106f6-107">datetime</span></span>|  
|<span data-ttu-id="106f6-108">decimal</span><span class="sxs-lookup"><span data-stu-id="106f6-108">decimal</span></span>|<span data-ttu-id="106f6-109">double</span><span class="sxs-lookup"><span data-stu-id="106f6-109">double</span></span>|<span data-ttu-id="106f6-110">int16</span><span class="sxs-lookup"><span data-stu-id="106f6-110">int16</span></span>|<span data-ttu-id="106f6-111">int32</span><span class="sxs-lookup"><span data-stu-id="106f6-111">int32</span></span>|  
|<span data-ttu-id="106f6-112">int64</span><span class="sxs-lookup"><span data-stu-id="106f6-112">int64</span></span>|<span data-ttu-id="106f6-113">long</span><span class="sxs-lookup"><span data-stu-id="106f6-113">long</span></span>|<span data-ttu-id="106f6-114">sbyte</span><span class="sxs-lookup"><span data-stu-id="106f6-114">sbyte</span></span>|<span data-ttu-id="106f6-115">single</span><span class="sxs-lookup"><span data-stu-id="106f6-115">single</span></span>|  
|<span data-ttu-id="106f6-116">string</span><span class="sxs-lookup"><span data-stu-id="106f6-116">string</span></span>|<span data-ttu-id="106f6-117">timespan</span><span class="sxs-lookup"><span data-stu-id="106f6-117">timespan</span></span>|<span data-ttu-id="106f6-118">uint16</span><span class="sxs-lookup"><span data-stu-id="106f6-118">uint16</span></span>|<span data-ttu-id="106f6-119">uint32</span><span class="sxs-lookup"><span data-stu-id="106f6-119">uint32</span></span>|  
|<span data-ttu-id="106f6-120">uint64</span><span class="sxs-lookup"><span data-stu-id="106f6-120">uint64</span></span>||||  
  
 <span data-ttu-id="106f6-121">还可以声明您的项目所引用的基于 .NET 的任意类型的变量。</span><span class="sxs-lookup"><span data-stu-id="106f6-121">You can also declare variables of any .NET-based types that are referenced in your project.</span></span>  
  
## <a name="considerations-for-declare-orchestration-variables"></a><span data-ttu-id="106f6-122">声明业务流程变量的注意事项</span><span class="sxs-lookup"><span data-stu-id="106f6-122">Considerations for Declare Orchestration Variables</span></span>  
 <span data-ttu-id="106f6-123">声明业务流程变量时，请注意以下事项：</span><span class="sxs-lookup"><span data-stu-id="106f6-123">When declare orchestration variables, consider the following:</span></span>  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="106f6-124">支持多值的上下文属性对于某些基于内容的路由方案，但你无法在业务流程中使用此类属性。</span><span class="sxs-lookup"><span data-stu-id="106f6-124"> supports multivalued context properties for certain content-based routing scenarios, but you cannot use such properties in orchestrations.</span></span>  
  
-   <span data-ttu-id="106f6-125">为支持业务流程的挂起和解除冻结，所有业务流程变量必须能够保持自身的状态。</span><span class="sxs-lookup"><span data-stu-id="106f6-125">In order to support suspension and re-hydration of orchestrations, all orchestration variables must be capable of having their state persisted.</span></span>  <span data-ttu-id="106f6-126">通常，这是通过对变量的类型或类进行序列化或流式处理来实现的。</span><span class="sxs-lookup"><span data-stu-id="106f6-126">Typically, this is accomplished by the variable's type or class being serializable or streamable.</span></span>  
  
-   <span data-ttu-id="106f6-127">这些基于 .NET 的类型（类）必须是可序列化的类。</span><span class="sxs-lookup"><span data-stu-id="106f6-127">These .NET-based types (classes) must be serializable classes.</span></span>  <span data-ttu-id="106f6-128">通过使用“[Serializable]”属性进行声明或通过显式实现 ISerializable .NET 接口（在 System.Runtime.Serialization 命名空间中），可以实现这些类型（类）的序列化。</span><span class="sxs-lookup"><span data-stu-id="106f6-128">They may either implement this by being declared with the "[Serializable]” attribute or by explicitly implementing the ISerializable .NET interface (in the System.Runtime.Serialization namespace).</span></span>  
  
-   <span data-ttu-id="106f6-129">如果基于 .NET 的类型实际上是某个底层 COM 组件的运行库可调用包装 (RCW)，那么该 COM 组件必须实现相应接口，RCW 才能成为可序列化的 .NET 类（例如 IPersistStream、IPersistStreamInit）。</span><span class="sxs-lookup"><span data-stu-id="106f6-129">If the .NET-based type is actually a runtime callable wrapper (RCW) of an underlying COM component, then that COM component must implement the interface(s) required for the RCW to be a serializable .NET class (e.g. IPersistStream, IPersistStreamInit).</span></span>  
  
-   <span data-ttu-id="106f6-130">由于所有基于 .NET 的类型（或底层 COM）均在业务流程内部执行，这些类型中的方法不能延迟业务流程的执行（例如，通过资源争用等方式）。</span><span class="sxs-lookup"><span data-stu-id="106f6-130">Because any .NET-based (or underlying COM) types are executing within the flow of an orchestration, methods in these types must not delay execution of the orchestration (e.g. through contention for resources, etc.).</span></span>  <span data-ttu-id="106f6-131">而且，这些类型实现对资源的任何消耗将影响运行调用业务流程的主机实例。</span><span class="sxs-lookup"><span data-stu-id="106f6-131">And any consumption of resources by these type implementations will affect the host instance in which the calling orchestration runs.</span></span>