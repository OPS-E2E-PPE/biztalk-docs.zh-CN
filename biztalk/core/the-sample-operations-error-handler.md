---
title: 示例操作错误处理程序 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Ops adapters, error handler
- process management solution tutorial, Ops adapters
ms.assetid: e6c55f01-c004-4340-beaa-d77764ae34c1
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 93536733c884b4d5db57ba18619ebabdead17561
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279621"
---
# <a name="the-sample-operations-error-handler"></a><span data-ttu-id="df1ee-102">操作错误处理程序示例</span><span class="sxs-lookup"><span data-stu-id="df1ee-102">The Sample Operations Error Handler</span></span>
<span data-ttu-id="df1ee-103">示例操作错误处理程序有三个主要的程序集： **OperationsClient**， **OperationsHandler**，和**OperationsServer**。</span><span class="sxs-lookup"><span data-stu-id="df1ee-103">The sample operations error handler has three major assemblies: **OperationsClient**, **OperationsHandler**, and **OperationsServer**.</span></span>  
  
 <span data-ttu-id="df1ee-104">解决方案配置的适配器以使用**OpsClient**对象在**OperationsClient**程序集。</span><span class="sxs-lookup"><span data-stu-id="df1ee-104">The solution configures the adapter to use the **OpsClient** object in the **OperationsClient** assembly.</span></span> <span data-ttu-id="df1ee-105">如你所料， **OpsClient**对象实现**IOpsAIC**接口。</span><span class="sxs-lookup"><span data-stu-id="df1ee-105">As you'd expect, the **OpsClient** object implements the **IOpsAIC** interface.</span></span>  
  
 <span data-ttu-id="df1ee-106">**OpsClient**对象使用**IOperationsSystem**接口来调用**OpsHandler**对象通过[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]远程处理功能。</span><span class="sxs-lookup"><span data-stu-id="df1ee-106">The **OpsClient** object uses the **IOperationsSystem** interface to call the **OpsHandler** object through the [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] remoting feature.</span></span> <span data-ttu-id="df1ee-107">**IOperationsSystem**接口如下所示：</span><span class="sxs-lookup"><span data-stu-id="df1ee-107">The **IOperationsSystem** interface appears as follows:</span></span>  
  
```  
public interface IOperationsSystem  
{  
    void Initialize(string initData);  
    void Post(string originMachine, byte[] message);  
}  
  
```  
  
 <span data-ttu-id="df1ee-108">**OperationsServer**，控制台应用程序，侦听请求**OpsHandler**对象，并充当服务器[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]远程处理功能。</span><span class="sxs-lookup"><span data-stu-id="df1ee-108">The **OperationsServer**, a console application, listens for requests for the **OpsHandler** object and acts as the server for the [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] remoting feature.</span></span> <span data-ttu-id="df1ee-109">调用**执行**方法**OpsClient**对象反过来调用**Post**方法**OpsHandler**对象。</span><span class="sxs-lookup"><span data-stu-id="df1ee-109">Calling the **Execute** method of the **OpsClient** object in turn invokes the **Post** method of the **OpsHandler** object.</span></span>  
  
 <span data-ttu-id="df1ee-110">**OpsHandler**方法响应通过写出使用其自变量字符串**跟踪**对象。</span><span class="sxs-lookup"><span data-stu-id="df1ee-110">The **OpsHandler** methods respond by writing out their argument strings using the **Trace** object.</span></span> <span data-ttu-id="df1ee-111">这会将错误发布到控制台。</span><span class="sxs-lookup"><span data-stu-id="df1ee-111">This posts the errors to the console.</span></span> <span data-ttu-id="df1ee-112">有关详细信息**跟踪**对象，请参阅中的"跟踪类"[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]类库。</span><span class="sxs-lookup"><span data-stu-id="df1ee-112">For more information about the **Trace** object, see "Trace Class" in the [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] Class Library.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="df1ee-113">此处的模式是，在相同**OrderHandler**接口在其中指定客户端与远程对象之间的方法调用。</span><span class="sxs-lookup"><span data-stu-id="df1ee-113">The pattern here is the same as that in the **OrderHandler** in which an interface specifies the method calls between a client and a remoted object.</span></span> <span data-ttu-id="df1ee-114">不存在，但是，其他之间的间接层此处**OpsClient**和**OpsHandler**。</span><span class="sxs-lookup"><span data-stu-id="df1ee-114">There is, however, an additional layer of indirection here between the **OpsClient** and the **OpsHandler**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df1ee-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="df1ee-115">See Also</span></span>  
 [<span data-ttu-id="df1ee-116">Ops 适配器</span><span class="sxs-lookup"><span data-stu-id="df1ee-116">The Ops Adapter</span></span>](../core/the-ops-adapter.md)