---
title: 组件接口用户定义的方法 |Microsoft 文档
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
ms.openlocfilehash: 139117ffb26c8fec355dcfe481657817bc64bc0b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233829"
---
# <a name="component-interface-user-defined-methods"></a><span data-ttu-id="be7d5-102">组件接口用户定义的方法</span><span class="sxs-lookup"><span data-stu-id="be7d5-102">Component Interface User-Defined Methods</span></span>
<span data-ttu-id="be7d5-103">用于 PeopleSoft Enterprise 的 Microsoft BizTalk 适配器在组件接口中支持用户定义的方法。</span><span class="sxs-lookup"><span data-stu-id="be7d5-103">Microsoft BizTalk Adapter for PeopleSoft Enterprise supports user-defined methods in component interfaces.</span></span> <span data-ttu-id="be7d5-104">签名形式如下：</span><span class="sxs-lookup"><span data-stu-id="be7d5-104">The signatures are of the form:</span></span>  
  
```  
myRet=myCI.myMethod(parameter1, parameter2, ...)  
```  
  
 <span data-ttu-id="be7d5-105">其中：</span><span class="sxs-lookup"><span data-stu-id="be7d5-105">where:</span></span>  
  
-   <span data-ttu-id="be7d5-106">`parameter1` 和 `parameter2` 为输入参数。</span><span class="sxs-lookup"><span data-stu-id="be7d5-106">`parameter1`, `parameter2` are input parameters.</span></span>  
  
-   <span data-ttu-id="be7d5-107">`myRet` 为返回值。</span><span class="sxs-lookup"><span data-stu-id="be7d5-107">`myRet` is the return value.</span></span>  
  
 <span data-ttu-id="be7d5-108">这些参数只能是该方法的输入参数。</span><span class="sxs-lookup"><span data-stu-id="be7d5-108">The parameters can only be input parameters to the method.</span></span> <span data-ttu-id="be7d5-109">可能从该方法返回一个值作为返回参数。</span><span class="sxs-lookup"><span data-stu-id="be7d5-109">Only one value can be returned from the method as the return parameter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="be7d5-110">包含用户定义方法的组件接口应该仅启用 PeopleSoft `Get` 函数。</span><span class="sxs-lookup"><span data-stu-id="be7d5-110">The component interface that contains user-defined methods should only have the PeopleSoft `Get` function enabled.</span></span> <span data-ttu-id="be7d5-111">如果组件接口具有密钥，则自定义方法将不起作用。</span><span class="sxs-lookup"><span data-stu-id="be7d5-111">If the component interface has keys, then custom methods will not work.</span></span>  
  
## <a name="custom-ci-limitation"></a><span data-ttu-id="be7d5-112">自定义 CI 限制</span><span class="sxs-lookup"><span data-stu-id="be7d5-112">Custom CI Limitation</span></span>  
 <span data-ttu-id="be7d5-113">用于 PeopleSoft Enterprise 的 BizTalk 适配器可以处理自定义 PeopleSoft 方法（假设组件接口不具有密钥）。</span><span class="sxs-lookup"><span data-stu-id="be7d5-113">BizTalk Adapter for PeopleSoft Enterprise can handle custom PeopleSoft methods provided that the component interface does not have keys.</span></span> <span data-ttu-id="be7d5-114">如果组件接口具有密钥，自定义方法不起作用。</span><span class="sxs-lookup"><span data-stu-id="be7d5-114">If the component interface has keys, custom methods will not work.</span></span>  
  
### <a name="workaround"></a><span data-ttu-id="be7d5-115">解决方法</span><span class="sxs-lookup"><span data-stu-id="be7d5-115">Workaround</span></span>  
 <span data-ttu-id="be7d5-116">创建一个不具有密钥的新组件接口，并编写一个将密钥合并为调用参数一部分的新自定义方法。</span><span class="sxs-lookup"><span data-stu-id="be7d5-116">Create a new component interface that does not have keys, and write a new custom method that incorporates the keys as part of the calling parameters.</span></span> <span data-ttu-id="be7d5-117">例如，可以在 USER_PROFILE 组件接口中使用 SetPassword 自定义方法；但是，USER_PROFILE 具有密钥。</span><span class="sxs-lookup"><span data-stu-id="be7d5-117">For example, you could use the SetPassword custom method in the USER_PROFILE component interface; however USER_PROFILE has keys.</span></span> <span data-ttu-id="be7d5-118">您可以创建一个不具有密钥的新组件接口，然后在新组件接口中创建一个自定义方法。</span><span class="sxs-lookup"><span data-stu-id="be7d5-118">You can create a new component interface that has no keys, and then create a custom method in your new component interface.</span></span> <span data-ttu-id="be7d5-119">此方法将接受两个参数，用户 ID 和密码。</span><span class="sxs-lookup"><span data-stu-id="be7d5-119">This method would accept two parameters, user ID and password.</span></span> <span data-ttu-id="be7d5-120">随后，自定义方法可以使用 `Get` 调用 USER_PROFILE，然后调用 `SetPassword`。</span><span class="sxs-lookup"><span data-stu-id="be7d5-120">The custom method could then invoke USER_PROFILE with a `Get` and then invoke `SetPassword`.</span></span> <span data-ttu-id="be7d5-121">有关详细信息，请参考 PeopleSoft 文档。</span><span class="sxs-lookup"><span data-stu-id="be7d5-121">Consult the PeopleSoft documentation for more details.</span></span>  
  
 <span data-ttu-id="be7d5-122">由于 PeopleSoft 的限制，用户定义方法中显示的 `Date`、`DateTime` 和 `Time` 类型将映射为客户端代码中的字符串。</span><span class="sxs-lookup"><span data-stu-id="be7d5-122">Due to a limitation in PeopleSoft, `Date`, `DateTime`, and `Time` types appearing in user-defined methods are mapped as strings in the client code.</span></span>  
  
## <a name="collection-limitation"></a><span data-ttu-id="be7d5-123">集合限制</span><span class="sxs-lookup"><span data-stu-id="be7d5-123">Collection Limitation</span></span>  
 <span data-ttu-id="be7d5-124">用户定义的方法通常无法返回一个或多个集合以及任何 API 对象。</span><span class="sxs-lookup"><span data-stu-id="be7d5-124">User-defined methods cannot return a collection, or more generally, any API object.</span></span> <span data-ttu-id="be7d5-125">这意味着只能返回字符串和数字等简单类型。</span><span class="sxs-lookup"><span data-stu-id="be7d5-125">This means that you can only return simple types, for example, strings and numbers.</span></span> <span data-ttu-id="be7d5-126">您可以解除此限制，方法是将集合作为 XML 字符串发送并对客户端进行编程以解析字符串，从而将项目提取到正确的格式。</span><span class="sxs-lookup"><span data-stu-id="be7d5-126">You can get around this limitation by sending a collection as an XML string and programming the client to parse the strings to extract the items into the correct format.</span></span> <span data-ttu-id="be7d5-127">您可以检查 GET_CI_INFO 自定义组件接口，以查看此解决方法的示例。</span><span class="sxs-lookup"><span data-stu-id="be7d5-127">You can examine the GET_CI_INFO custom component interface to see an example of this workaround.</span></span>  
  
## <a name="sample-custom-method"></a><span data-ttu-id="be7d5-128">示例自定义方法</span><span class="sxs-lookup"><span data-stu-id="be7d5-128">Sample Custom Method</span></span>  
 <span data-ttu-id="be7d5-129">您可以使用以下基本自定义方法，SayHello，以便使用自定义方法来测试组件接口的功能。</span><span class="sxs-lookup"><span data-stu-id="be7d5-129">You can use the following basic custom method, SayHello, to test the functionality of your component interface using custom methods.</span></span>  
  
 <span data-ttu-id="be7d5-130">以下 PeopleCode 函数是 PeopleSoft 组件接口的一个用户定义的方法，名为 ACB_EMPLOYEE。</span><span class="sxs-lookup"><span data-stu-id="be7d5-130">The following PeopleCode function is a user-defined method of a PeopleSoft component interface named ACB_EMPLOYEE.</span></span> <span data-ttu-id="be7d5-131">此示例返回一个字符串，其中的返回值是**Hello**跟输入参数的值。</span><span class="sxs-lookup"><span data-stu-id="be7d5-131">The sample returns a string where the return value is **Hello** followed by the value of the input parameter.</span></span>  
  
```  
Function SayHello(&sName As string) Returns string  
      &EOL = Char(10);  
      &sResult = "Hello " | &sName | &EOL;  
      Return &sResult;  
End-Function;  
```  
  
> [!NOTE]
>  <span data-ttu-id="be7d5-132">若要使用一个命令同时对多个表进行修改，可以创建另一个组件接口，或创建组件接口用户定义方法。</span><span class="sxs-lookup"><span data-stu-id="be7d5-132">To modify multiple tables at the same time (using one command) you can either create another component interface or create a component interface user-defined method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be7d5-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="be7d5-133">See Also</span></span>  
 [<span data-ttu-id="be7d5-134">附录 a： 组件接口方法</span><span class="sxs-lookup"><span data-stu-id="be7d5-134">Appendix A: Component Interface Methods</span></span>](../core/appendix-a-component-interface-methods.md)