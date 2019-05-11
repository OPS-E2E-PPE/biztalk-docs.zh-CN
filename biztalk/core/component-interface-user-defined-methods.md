---
title: 组件接口用户定义的方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- component interfaces, user-defined methods
- user-defined methods, component interface
- custom component interfaces, limitations
- collection limitations
- custom methods, samples
- samples, custom methods
- component interfaces, limitations for custom CI
ms.assetid: e4b15889-35ff-44aa-819d-eade9690bdd6
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1574a73b45f5048910d5df8fee43d75502c2938b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356717"
---
# <a name="component-interface-user-defined-methods"></a><span data-ttu-id="2ef34-102">组件接口用户定义的方法</span><span class="sxs-lookup"><span data-stu-id="2ef34-102">Component Interface User-Defined Methods</span></span>
<span data-ttu-id="2ef34-103">用于 PeopleSoft Enterprise 的 Microsoft BizTalk 适配器在组件接口中支持用户定义的方法。</span><span class="sxs-lookup"><span data-stu-id="2ef34-103">Microsoft BizTalk Adapter for PeopleSoft Enterprise supports user-defined methods in component interfaces.</span></span> <span data-ttu-id="2ef34-104">签名是窗体：</span><span class="sxs-lookup"><span data-stu-id="2ef34-104">The signatures are of the form:</span></span>  
  
```  
myRet=myCI.myMethod(parameter1, parameter2, ...)  
```  
  
 <span data-ttu-id="2ef34-105">其中：</span><span class="sxs-lookup"><span data-stu-id="2ef34-105">where:</span></span>  
  
- <span data-ttu-id="2ef34-106">`parameter1``parameter2`是输入的参数。</span><span class="sxs-lookup"><span data-stu-id="2ef34-106">`parameter1`, `parameter2` are input parameters.</span></span>  
  
- <span data-ttu-id="2ef34-107">`myRet` 是返回值。</span><span class="sxs-lookup"><span data-stu-id="2ef34-107">`myRet` is the return value.</span></span>  
  
  <span data-ttu-id="2ef34-108">参数只能是该方法的输入的参数。</span><span class="sxs-lookup"><span data-stu-id="2ef34-108">The parameters can only be input parameters to the method.</span></span> <span data-ttu-id="2ef34-109">可以从方法返回一个值，作为返回参数。</span><span class="sxs-lookup"><span data-stu-id="2ef34-109">Only one value can be returned from the method as the return parameter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2ef34-110">包含用户定义的方法的组件接口应该只有 PeopleSoft`Get`函数启用。</span><span class="sxs-lookup"><span data-stu-id="2ef34-110">The component interface that contains user-defined methods should only have the PeopleSoft `Get` function enabled.</span></span> <span data-ttu-id="2ef34-111">如果组件接口具有密钥，然后自定义方法将不起作用。</span><span class="sxs-lookup"><span data-stu-id="2ef34-111">If the component interface has keys, then custom methods will not work.</span></span>  
  
## <a name="custom-ci-limitation"></a><span data-ttu-id="2ef34-112">自定义 CI 限制</span><span class="sxs-lookup"><span data-stu-id="2ef34-112">Custom CI Limitation</span></span>  
 <span data-ttu-id="2ef34-113">用于 PeopleSoft Enterprise 的 BizTalk 适配器可以处理自定义 PeopleSoft 方法，前提是组件接口没有键。</span><span class="sxs-lookup"><span data-stu-id="2ef34-113">BizTalk Adapter for PeopleSoft Enterprise can handle custom PeopleSoft methods provided that the component interface does not have keys.</span></span> <span data-ttu-id="2ef34-114">如果组件接口具有密钥，自定义方法将不起作用。</span><span class="sxs-lookup"><span data-stu-id="2ef34-114">If the component interface has keys, custom methods will not work.</span></span>  
  
### <a name="workaround"></a><span data-ttu-id="2ef34-115">解决方法</span><span class="sxs-lookup"><span data-stu-id="2ef34-115">Workaround</span></span>  
 <span data-ttu-id="2ef34-116">创建一个新的组件接口，它不具有键，编写新的自定义方法，将密钥合并为调用的参数的一部分。</span><span class="sxs-lookup"><span data-stu-id="2ef34-116">Create a new component interface that does not have keys, and write a new custom method that incorporates the keys as part of the calling parameters.</span></span> <span data-ttu-id="2ef34-117">例如，可以在 USER_PROFILE 组件接口; 使用 SetPassword 自定义方法但是，USER_PROFILE 具有密钥。</span><span class="sxs-lookup"><span data-stu-id="2ef34-117">For example, you could use the SetPassword custom method in the USER_PROFILE component interface; however USER_PROFILE has keys.</span></span> <span data-ttu-id="2ef34-118">可以创建新的组件接口没有键，，然后在新的组件接口中创建自定义方法。</span><span class="sxs-lookup"><span data-stu-id="2ef34-118">You can create a new component interface that has no keys, and then create a custom method in your new component interface.</span></span> <span data-ttu-id="2ef34-119">此方法将接受两个参数，用户 ID 和密码。</span><span class="sxs-lookup"><span data-stu-id="2ef34-119">This method would accept two parameters, user ID and password.</span></span> <span data-ttu-id="2ef34-120">自定义的方法可以调用与 USER_PROFILE `Get` ，然后调用`SetPassword`。</span><span class="sxs-lookup"><span data-stu-id="2ef34-120">The custom method could then invoke USER_PROFILE with a `Get` and then invoke `SetPassword`.</span></span> <span data-ttu-id="2ef34-121">有关详细信息，请参阅 PeopleSoft 文档。</span><span class="sxs-lookup"><span data-stu-id="2ef34-121">Consult the PeopleSoft documentation for more details.</span></span>  
  
 <span data-ttu-id="2ef34-122">由于在 PeopleSoft 的限制`Date`， `DateTime`，和`Time`出现在用户定义的方法的类型将映射为客户端代码中的字符串。</span><span class="sxs-lookup"><span data-stu-id="2ef34-122">Due to a limitation in PeopleSoft, `Date`, `DateTime`, and `Time` types appearing in user-defined methods are mapped as strings in the client code.</span></span>  
  
## <a name="collection-limitation"></a><span data-ttu-id="2ef34-123">集合限制</span><span class="sxs-lookup"><span data-stu-id="2ef34-123">Collection Limitation</span></span>  
 <span data-ttu-id="2ef34-124">用户定义的方法不能返回一个集合，或多个通常情况下，任何 API 对象。</span><span class="sxs-lookup"><span data-stu-id="2ef34-124">User-defined methods cannot return a collection, or more generally, any API object.</span></span> <span data-ttu-id="2ef34-125">这意味着，您可以只返回简单类型，例如，字符串和数字。</span><span class="sxs-lookup"><span data-stu-id="2ef34-125">This means that you can only return simple types, for example, strings and numbers.</span></span> <span data-ttu-id="2ef34-126">您可以避开此限制通过发送作为 XML 字符串的集合和客户端编程以解析字符串，以将项目提取到正确的格式。</span><span class="sxs-lookup"><span data-stu-id="2ef34-126">You can get around this limitation by sending a collection as an XML string and programming the client to parse the strings to extract the items into the correct format.</span></span> <span data-ttu-id="2ef34-127">您可以检查 GET_CI_INFO 自定义组件接口，以查看此解决方法的示例。</span><span class="sxs-lookup"><span data-stu-id="2ef34-127">You can examine the GET_CI_INFO custom component interface to see an example of this workaround.</span></span>  
  
## <a name="sample-custom-method"></a><span data-ttu-id="2ef34-128">示例自定义方法</span><span class="sxs-lookup"><span data-stu-id="2ef34-128">Sample Custom Method</span></span>  
 <span data-ttu-id="2ef34-129">以下基本自定义方法，SayHello，可用于测试组件接口使用自定义方法的功能。</span><span class="sxs-lookup"><span data-stu-id="2ef34-129">You can use the following basic custom method, SayHello, to test the functionality of your component interface using custom methods.</span></span>  
  
 <span data-ttu-id="2ef34-130">以下 PeopleCode 函数是名为 ACB_EMPLOYEE PeopleSoft 组件接口的一个用户定义的方法。</span><span class="sxs-lookup"><span data-stu-id="2ef34-130">The following PeopleCode function is a user-defined method of a PeopleSoft component interface named ACB_EMPLOYEE.</span></span> <span data-ttu-id="2ef34-131">该示例返回一个字符串，其中的返回值是**Hello**跟输入参数的值。</span><span class="sxs-lookup"><span data-stu-id="2ef34-131">The sample returns a string where the return value is **Hello** followed by the value of the input parameter.</span></span>  
  
```  
Function SayHello(&sName As string) Returns string  
      &EOL = Char(10);  
      &sResult = "Hello " | &sName | &EOL;  
      Return &sResult;  
End-Function;  
```  
  
> [!NOTE]
>  <span data-ttu-id="2ef34-132">（使用一个命令） 的同时修改多个表可以创建另一个组件接口，或创建一个组件接口用户定义的方法。</span><span class="sxs-lookup"><span data-stu-id="2ef34-132">To modify multiple tables at the same time (using one command) you can either create another component interface or create a component interface user-defined method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ef34-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="2ef34-133">See Also</span></span>  
 [<span data-ttu-id="2ef34-134">附录 a:组件接口方法</span><span class="sxs-lookup"><span data-stu-id="2ef34-134">Appendix A: Component Interface Methods</span></span>](../core/appendix-a-component-interface-methods.md)