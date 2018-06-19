---
title: 在服务中有效地使用 SSO 面向解决方案 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SSO, service solutions
- service solution tutorial, SSO
- SSO, using from code
ms.assetid: 809e0ad3-cc7f-4095-87d1-63031675a47f
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 66dafba56bdeedb8c7b35b4442623f55e70f1305
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289261"
---
# <a name="using-sso-efficiently-in-the-service-oriented-solution"></a><span data-ttu-id="ddc6f-102">在服务中有效地使用 SSO 面向解决方案</span><span class="sxs-lookup"><span data-stu-id="ddc6f-102">Using SSO Efficiently in the Service Oriented Solution</span></span>
<span data-ttu-id="ddc6f-103">面向服务的解决方案使用企业单一登录 (SSO) 来存储配置值和处理后端系统的凭据。</span><span class="sxs-lookup"><span data-stu-id="ddc6f-103">The service oriented solution uses Enterprise Single Sign-On (SSO) both to store configuration values and to handle credentials for the back-end systems.</span></span> <span data-ttu-id="ddc6f-104">为缩短延迟时间，该解决方案使用本地缓存来存储配置值。</span><span class="sxs-lookup"><span data-stu-id="ddc6f-104">To reduce latency, the solution uses a local cache for the configuration values.</span></span> <span data-ttu-id="ddc6f-105">该解决方案每隔五分钟刷新一次缓存。</span><span class="sxs-lookup"><span data-stu-id="ddc6f-105">The solution refreshes the cache every five minutes.</span></span>  
  
 <span data-ttu-id="ddc6f-106">在许多应用程序中，都使用适配器来处理 SSO 操作，包括获取 SSO 票证，兑换票证，以及使用凭据来获取对关联应用程序的访问。</span><span class="sxs-lookup"><span data-stu-id="ddc6f-106">In many applications, the adapters handle the SSO operations—including getting an SSO ticket, redeeming the ticket, and using the credentials to gain access to the affiliate application.</span></span> <span data-ttu-id="ddc6f-107">但是，面向服务的解决方案的内联版本不使用适配器。</span><span class="sxs-lookup"><span data-stu-id="ddc6f-107">However, the inline version of the service oriented solution does not use adapters.</span></span> <span data-ttu-id="ddc6f-108">它必须通过代码使用 SSO。</span><span class="sxs-lookup"><span data-stu-id="ddc6f-108">It must use SSO from code.</span></span>  
  
 <span data-ttu-id="ddc6f-109">本主题介绍了该解决方案所使用的缓存机制，以及该解决方案的内联版本如何通过代码使用 SSO。</span><span class="sxs-lookup"><span data-stu-id="ddc6f-109">This topic describes the caching mechanism used by the solution, as well as how the inline version of the solution uses SSO from code.</span></span>  
  
## <a name="local-caching-of-configuration-values"></a><span data-ttu-id="ddc6f-110">本地缓存的配置值</span><span class="sxs-lookup"><span data-stu-id="ddc6f-110">Local Caching of Configuration Values</span></span>  
 <span data-ttu-id="ddc6f-111">面向服务解决方案使用两个对象， **ConfigPropertyBag**和**ConfigParameters**，目的是处理的配置值。</span><span class="sxs-lookup"><span data-stu-id="ddc6f-111">The service oriented solution uses two objects, **ConfigPropertyBag** and **ConfigParameters**, to handle the configuration values.</span></span> <span data-ttu-id="ddc6f-112">**ConfigPropertyBag**类保持值，并仅供**ConfigParameters**类。</span><span class="sxs-lookup"><span data-stu-id="ddc6f-112">The **ConfigPropertyBag** class holds the values and is used only by the **ConfigParameters** class.</span></span> <span data-ttu-id="ddc6f-113">**ConfigParameters**解决方案的其他部分使用类来检索的配置参数。</span><span class="sxs-lookup"><span data-stu-id="ddc6f-113">The **ConfigParameters** class is used by the other parts of the solution to retrieve the configuration parameters.</span></span> <span data-ttu-id="ddc6f-114">这两个类位于**Microsoft.Samples.BizTalk.WoodgroveBank.ConfigHelper**命名空间。</span><span class="sxs-lookup"><span data-stu-id="ddc6f-114">Both classes are in the **Microsoft.Samples.BizTalk.WoodgroveBank.ConfigHelper** namespace.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ddc6f-115">面向服务的解决方案将缓存刷新间隔固定为 300 秒（5 分钟）。</span><span class="sxs-lookup"><span data-stu-id="ddc6f-115">The Service Oriented solution fixes the cache refresh interval at 300 seconds (5 minutes).</span></span> <span data-ttu-id="ddc6f-116">当然，您可能希望将缓存刷新间隔本身作为该解决方案中的一个可配置的属性。</span><span class="sxs-lookup"><span data-stu-id="ddc6f-116">You may, instead, want to make the cache refresh interval itself  a configurable property in this solution.</span></span> <span data-ttu-id="ddc6f-117">在业务流程管理解决方案中就是这么做的。</span><span class="sxs-lookup"><span data-stu-id="ddc6f-117">This is done in the Business Process Management solution.</span></span> <span data-ttu-id="ddc6f-118">有关该解决方案如何处理 SSO 的详细信息，请参阅[业务流程管理解决方案中有效使用 SSO](../core/using-sso-efficiently-in-the-business-process-management-solution.md)。</span><span class="sxs-lookup"><span data-stu-id="ddc6f-118">For more information about how that solution handles SSO, see [Using SSO Efficiently in the Business Process Management Solution](../core/using-sso-efficiently-in-the-business-process-management-solution.md).</span></span> <span data-ttu-id="ddc6f-119">请注意，在这种情况下，对刷新间隔所做的更改直到在原有间隔结束时发生的刷新缓存之后才会生效。</span><span class="sxs-lookup"><span data-stu-id="ddc6f-119">Notice that, in such a case, a change in the refresh interval does not take effect until the cache is refreshed at the end of the old interval time.</span></span>  
  
 <span data-ttu-id="ddc6f-120">**ConfigPropertyBag**具有以下方法：</span><span class="sxs-lookup"><span data-stu-id="ddc6f-120">The **ConfigPropertyBag** has the following methods:</span></span>  
  
|<span data-ttu-id="ddc6f-121">方法</span><span class="sxs-lookup"><span data-stu-id="ddc6f-121">Method</span></span>|<span data-ttu-id="ddc6f-122">Description</span><span class="sxs-lookup"><span data-stu-id="ddc6f-122">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="ddc6f-123">读取</span><span class="sxs-lookup"><span data-stu-id="ddc6f-123">Read</span></span>|<span data-ttu-id="ddc6f-124">检索给定属性的值。</span><span class="sxs-lookup"><span data-stu-id="ddc6f-124">Retrieves a value for a given property.</span></span>|  
|<span data-ttu-id="ddc6f-125">写入</span><span class="sxs-lookup"><span data-stu-id="ddc6f-125">Write</span></span>|<span data-ttu-id="ddc6f-126">为属性赋值。</span><span class="sxs-lookup"><span data-stu-id="ddc6f-126">Assigns a value to a property.</span></span>|  
  
 <span data-ttu-id="ddc6f-127">类使用的.NET 实例**NameValueCollection**以保存的值。</span><span class="sxs-lookup"><span data-stu-id="ddc6f-127">The class uses an instance of a .NET **NameValueCollection** to hold the values.</span></span> <span data-ttu-id="ddc6f-128">两种访问方法实现**IPropertyBag**接口从**Microsoft.BizTalk.SSOClient.Interop**命名空间。</span><span class="sxs-lookup"><span data-stu-id="ddc6f-128">The two access methods implement the **IPropertyBag** interface from the **Microsoft.BizTalk.SSOClient.Interop** namespace.</span></span> <span data-ttu-id="ddc6f-129">**ConfigPropertyBag**类是一个内部的类，仅供**ConfigParameters**类。</span><span class="sxs-lookup"><span data-stu-id="ddc6f-129">The **ConfigPropertyBag** class is an internal class and used only by the **ConfigParameters** class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ddc6f-130">属性包中的键名不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="ddc6f-130">Key names in the property bag are case insensitive.</span></span> <span data-ttu-id="ddc6f-131">基础**NameValueCollection**使用不区分大小写的哈希算法和不区分大小写的比较。</span><span class="sxs-lookup"><span data-stu-id="ddc6f-131">The underlying **NameValueCollection** uses case-insensitive hashing and case-insensitive comparisons.</span></span>  
  
 <span data-ttu-id="ddc6f-132">应用程序使用**ConfigParameters**类用于处理的 SSO 配置值。</span><span class="sxs-lookup"><span data-stu-id="ddc6f-132">The application uses the **ConfigParameters** class to handle the SSO configuration values.</span></span> <span data-ttu-id="ddc6f-133">这个类具有以下公共方法和属性：</span><span class="sxs-lookup"><span data-stu-id="ddc6f-133">The class has the following public methods and attributes:</span></span>  
  
|<span data-ttu-id="ddc6f-134">方法或属性</span><span class="sxs-lookup"><span data-stu-id="ddc6f-134">Method or Attribute</span></span>|<span data-ttu-id="ddc6f-135">Description</span><span class="sxs-lookup"><span data-stu-id="ddc6f-135">Description</span></span>|  
|-------------------------|-----------------|  
|<span data-ttu-id="ddc6f-136">SSOConfigParameter</span><span class="sxs-lookup"><span data-stu-id="ddc6f-136">SSOConfigParameter</span></span>|<span data-ttu-id="ddc6f-137">用于指定配置参数的枚举。</span><span class="sxs-lookup"><span data-stu-id="ddc6f-137">An enumeration for specifying configuration parameters.</span></span>|  
|<span data-ttu-id="ddc6f-138">GetConfigParameters</span><span class="sxs-lookup"><span data-stu-id="ddc6f-138">GetConfigParameters</span></span>|<span data-ttu-id="ddc6f-139">用于检索给定参数值的方法。</span><span class="sxs-lookup"><span data-stu-id="ddc6f-139">A method used to retrieve a value for a given parameter.</span></span> <span data-ttu-id="ddc6f-140">使用 SSOConfigParameter 来指示该参数。</span><span class="sxs-lookup"><span data-stu-id="ddc6f-140">Uses the SSOConfigParameter to indicate the parameter.</span></span>|  
  
 <span data-ttu-id="ddc6f-141">**ConfigParameters**类使用.NET 计时器类和委托函数来设置的刷新**ConfigPropertyBag**:</span><span class="sxs-lookup"><span data-stu-id="ddc6f-141">The **ConfigParameters** class uses the .NET Timer class and a delegate function to set up the refresh of the **ConfigPropertyBag**:</span></span>  
  
```  
private static Timer cacheRefreshTimer;  
private static ISSOConfigStore ssoConfigStore;  
private static ReaderWriterLock syncLock;  
  
// Cache refresh interval in milliseconds  
private const int CacheRefreshInterval = 5 * 60 * 1000;  
private static ConfigPropertyBag ssoPropBag;  
  
static ConfigParameters()  
{  
    ssoConfigStore = new ISSOConfigStore();  
    ssoPropBag = new ConfigPropertyBag();  
    syncLock = new ReaderWriterLock();  
  
    ssoConfigStore.GetConfigInfo(SSO_CONFIG_APP,  
         SSO_IDENTIFIER_NAME, SSOFlag.SSO_FLAG_RUNTIME,  
         ssoPropBag);  
  
    cacheRefreshTimer = new Timer(  
        new TimerCallback(ConfigParameters.cacheRefreshCallback),  
        null, CacheRefreshInterval, CacheRefreshInterval);  
}  
```  
  
 <span data-ttu-id="ddc6f-142">请注意，静态构造函数初始化的是静态成员变量，因此即使不创建类实例也可以使用类方法。</span><span class="sxs-lookup"><span data-stu-id="ddc6f-142">Notice that the static constructor initializes the static member variables thus enabling the use of class methods without creating an instance of the class.</span></span> <span data-ttu-id="ddc6f-143">此构造函数创建的 SSO 配置存储区的实例 (**ISSOConfigStore**)，配置属性包 (**ConfigPropertyBag**)，和的同步锁定 (**ReaderWriterLock**) 用于控制对访问**ConfigurationPropertyBag**期间更新和读取。</span><span class="sxs-lookup"><span data-stu-id="ddc6f-143">The constructor creates instances of the SSO configuration store (**ISSOConfigStore**), the configuration property bag (**ConfigPropertyBag**), and a synchronization lock (**ReaderWriterLock**) used to control access to the **ConfigurationPropertyBag** during updates and reads.</span></span> <span data-ttu-id="ddc6f-144">然后，此构造函数使用**GetConfigInfo**检索 SSO 配置值并将它们放在属性包。</span><span class="sxs-lookup"><span data-stu-id="ddc6f-144">The constructor then uses **GetConfigInfo** to retrieve the SSO configuration values and to put them in the property bag.</span></span> <span data-ttu-id="ddc6f-145">最后，此构造函数创建**计时器**对象，指定的时间间隔之后, 将调用委托函数， **cacheRefreshCallback**。</span><span class="sxs-lookup"><span data-stu-id="ddc6f-145">Finally, the constructor creates a **Timer** object that, after the specified interval, calls the delegate function, **cacheRefreshCallback**.</span></span>  
  
 <span data-ttu-id="ddc6f-146">**计时器**委托函数是相对比较简单：</span><span class="sxs-lookup"><span data-stu-id="ddc6f-146">The **Timer** delegate function is relatively straightforward:</span></span>  
  
```  
private static void cacheRefreshCallback(object state)  
{  
    // Disable the timer until we are done loading the cache.  
    cacheRefreshTimer.Change(Timeout.Infinite, CacheRefreshInterval);  
  
    // Put the data from SSO in a new property bag so that  
    // we don't have to lock the property bag and block it from being  
    // used. The SSO call is a remote call and may take a while.  
    ConfigPropertyBag propBag2 = new ConfigPropertyBag();  
    ssoConfigStore.GetConfigInfo(SSO_CONFIG_APP,   
        SSO_IDENTIFIER_NAME, SSOFlag.SSO_FLAG_RUNTIME, propBag2);  
  
    // Get a writer lock before updating the cached values.  
    syncLock.AcquireWriterLock(Timeout.Infinite);  
  
    try  
    {  
        ssoPropBag = propBag2;  
    }  
    finally   
    {  
        syncLock.ReleaseWriterLock();  
    }  
    // Enable the timer.  
    cacheRefreshTimer.Change(CacheRefreshInterval,   
        CacheRefreshInterval);  
}  
```  
  
 <span data-ttu-id="ddc6f-147">请注意，cacheRefreshCallback 方法会禁用该计时器，以便该方法可以全程运行。</span><span class="sxs-lookup"><span data-stu-id="ddc6f-147">Notice that the cache refresh callback method disables the timer so that the method can run all the way through.</span></span> <span data-ttu-id="ddc6f-148">还要注意在控制对属性包的访问时锁的使用。</span><span class="sxs-lookup"><span data-stu-id="ddc6f-148">Also notice the use of the locks to control access to the property bag.</span></span> <span data-ttu-id="ddc6f-149">**ReaderWriterLock**是最佳选择 — 它的适用情况下在有多个读取超过写入。</span><span class="sxs-lookup"><span data-stu-id="ddc6f-149">The **ReaderWriterLock** is the best choice here—it is designed for cases where there are more reads than writes.</span></span> <span data-ttu-id="ddc6f-150">此外请注意，该锁， **syncLock**、 是静态的在类级别所有线程都共享相同的单个实例，它的声明。</span><span class="sxs-lookup"><span data-stu-id="ddc6f-150">Notice also that the lock, **syncLock**, is static and declared at the class level that all threads share the same, single instance of it.</span></span>  
  
## <a name="using-sso-from-code"></a><span data-ttu-id="ddc6f-151">通过代码使用 SSO</span><span class="sxs-lookup"><span data-stu-id="ddc6f-151">Using SSO from Code</span></span>  
 <span data-ttu-id="ddc6f-152">在使用代码中的单一登录时，该代码必须执行适配器的作用： 即，从消息中检索 SSO 票证、 兑换票证，以获取用户名和密码对于后端系统中，并在最后，使用后端系统。</span><span class="sxs-lookup"><span data-stu-id="ddc6f-152">When using single sign-on from code, the code must take on the role of the adapter: that is,retrieve the SSO ticket from the message, redeem the ticket to get the user name and password for the back-end system, and, finally, use the back-end system.</span></span> <span data-ttu-id="ddc6f-153">面向服务的解决方案执行此通过**GetPendingTransactionsResponse**方法**PendingTransactionsCaller**对象。</span><span class="sxs-lookup"><span data-stu-id="ddc6f-153">The service-oriented solution does this through the **GetPendingTransactionsResponse** method of the **PendingTransactionsCaller** object.</span></span>  
  
 <span data-ttu-id="ddc6f-154">该方法如下所示：</span><span class="sxs-lookup"><span data-stu-id="ddc6f-154">The method appears as follows:</span></span>  
  
```  
public static PendingTransactionsResponse GetPendingTransactionsResponse(XLANGMessage requestMsg)  
{  
    try  
    {  
        // Get config parameter values.  
        int ptTimeout = Convert.ToInt32(  
            ConfigParameters.GetConfigParameter(  
                ConfigParameters.  
                    SSOConfigParameter.  
                        PENDING_TRANSACTIONS_INLINE_TIMEOUT  
            )  
        );  
  
        string ptURL = ConfigParameters.GetConfigParameter(  
            ConfigParameters.  
                SSOConfigParameter.  
                    PENDING_TRANSACTIONS_URL  
        );  
        string ssoAffliateApp = ConfigParameters.  
            GetConfigParameter(ConfigParameters.  
                SSOConfigParameter.  
                    PENDING_TRANSACTIONS_SSO_AFFILIATE_APP  
            );  
  
        // Redeem the SSO ticket and get the userid/password to   
        // use to interact with Pending Transaction System.  
  
        // Extract the ticket…  
        string msgTicket = (string)requestMsg.  
            GetPropertyValue(typeof(BTS.SSOTicket));  
  
        // and the user name of the originating user.  
        string originatorSID = (string)requestMsg.  
            GetPropertyValue(  
                typeof(  
                    Microsoft.BizTalk.XLANGs.BTXEngine.OriginatorSID  
                )  
            );  
  
        string pendTransUserName;  
        // Now, redeem the ticket.  
        string[] pendTransCredential =   
            ssoTicket.RedeemTicket(  
                ssoAffliateApp,  
                originatorSID,  
                msgTicket,  
                SSOFlag.SSO_FLAG_NONE,  
                out pendTransUserName  
            );   
  
        PendingTransactionsRequest req =   
            (PendingTransactionsRequest)requestMsg[0].  
                RetrieveAs(  
                    typeof(PendingTransactionsRequest)  
                );  
        PendingTransactionsResponse resp;  
  
        using (PendingTransactionsWebService  
            svc = new PendingTransactionsWebService())  
        {  
            svc.Url = ptURL;  
            svc.Timeout = ptTimeout;  
  
            // The web service uses basic authentication, so we  
            //need to send the user id and password in the request.  
            CredentialCache credCache = new CredentialCache();  
            NetworkCredential credentialToUse =  
                new NetworkCredential(  
                    pendTransUserName, pendTransCredential[0]  
                );  
            credCache.Add(new Uri(svc.Url), "Basic", credentialToUse);  
            svc.Credentials = credCache;  
  
            resp = svc.GetPendingTransactions(req);  
        }  
        return resp;                  
    }  
    catch (System.Net.WebException webEx)  
    {  
        if (webEx.Status == WebExceptionStatus.Timeout)  
        {  
            throw new PendingTransactionsTimeoutException();  
        }  
        else  
        {  
            Trace.WriteLine("Other Net.WebException: "  
                + webEx.ToString()   
                + (null == webEx.InnerException ? "" :  
                     ("Inner Exception: "   
                        + webEx.InnerException.ToString())  
                )  
            );  
            throw;  
        }  
    }  
    catch(System.Exception ex)  
    {  
        Trace.WriteLine("Other Exception: "  
            + ex.ToString()   
            + (null == ex.InnerException ? "" :   
                 ("Inner Exception: "  
                    + ex.InnerException.ToString())  
                  )  
            );  
        throw;  
    }  
}  
```  
  
 <span data-ttu-id="ddc6f-155">该方法首先检索后端系统的配置信息（包括 URL）以及后端（关联）应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="ddc6f-155">The method begins by retrieving configuration information, including the URL, for the back-end system and the name of the backend (affiliate) application.</span></span>  
  
 <span data-ttu-id="ddc6f-156">为了兑换票证，该方法必须从消息中提取票证和原始请求用户名。</span><span class="sxs-lookup"><span data-stu-id="ddc6f-156">To redeem the ticket, the method must extract the ticket and original requesting user name from the message.</span></span> <span data-ttu-id="ddc6f-157">消息包含作为消息上下文属性中的一个票证**BTS。SSOTicket**。</span><span class="sxs-lookup"><span data-stu-id="ddc6f-157">The message contains the ticket as one of the message context properties, **BTS.SSOTicket**.</span></span> <span data-ttu-id="ddc6f-158">有关详细信息，请参阅**消息上下文属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="ddc6f-158">For more information, see **Message Context Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span> <span data-ttu-id="ddc6f-159">该方法还提取**OriginatorSID**从消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="ddc6f-159">The method also extracts the **OriginatorSID** from the message context properties.</span></span> <span data-ttu-id="ddc6f-160">有了票证和创建者名称后，该方法将对票证调用 RedeemTicket 方法以检索凭据。</span><span class="sxs-lookup"><span data-stu-id="ddc6f-160">With the ticket and the originator's name in hand, the method calls the RedeemTicket method on the ticket to retrieve the credentials.</span></span>  
  
 <span data-ttu-id="ddc6f-161">其余的代码将为凭据创建一个 .NET NetworkCredential 缓存，并调用后端 Web Services。</span><span class="sxs-lookup"><span data-stu-id="ddc6f-161">The remainder of the code creates a .NET NetworkCredential cache for the credentials and calls the back-end Web service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ddc6f-162">由于用户名和密码是以明文形式从 SSO 中返回的，因此应最大限度地缩短保存该信息的变量的生存期。</span><span class="sxs-lookup"><span data-stu-id="ddc6f-162">Because the user name and password come back from SSO in clear text, you want to minimize the lifetime of variables holding that information.</span></span> <span data-ttu-id="ddc6f-163">请注意此代码声明中的凭据变量**重**块。</span><span class="sxs-lookup"><span data-stu-id="ddc6f-163">Notice that the code declares the credential variables within a **try** block.</span></span> <span data-ttu-id="ddc6f-164">此处，变量退出之后都过期**重**块。</span><span class="sxs-lookup"><span data-stu-id="ddc6f-164">Here, the variables expire upon exit from the **try** block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddc6f-165">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ddc6f-165">See Also</span></span>  
 [<span data-ttu-id="ddc6f-166">服务实现重点介绍面向解决方案</span><span class="sxs-lookup"><span data-stu-id="ddc6f-166">Implementation Highlights of the Service Oriented Solution</span></span>](../core/implementation-highlights-of-the-service-oriented-solution.md)