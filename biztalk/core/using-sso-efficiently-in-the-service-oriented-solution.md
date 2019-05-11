---
title: 在服务中有效使用 SSO 面向解决方案 |Microsoft Docs
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
ms.openlocfilehash: 7e5f411ff3bc003966e001fa44c559a803bba991
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65321583"
---
# <a name="using-sso-efficiently-in-the-service-oriented-solution"></a><span data-ttu-id="398ab-102">在服务中有效使用 SSO 面向解决方案</span><span class="sxs-lookup"><span data-stu-id="398ab-102">Using SSO Efficiently in the Service Oriented Solution</span></span>
<span data-ttu-id="398ab-103">面向服务的解决方案使用企业单一登录 (SSO) 来存储配置值并处理后端系统的凭据。</span><span class="sxs-lookup"><span data-stu-id="398ab-103">The service oriented solution uses Enterprise Single Sign-On (SSO) both to store configuration values and to handle credentials for the back-end systems.</span></span> <span data-ttu-id="398ab-104">若要减少延迟，解决方案时，可使用本地缓存来存储配置值。</span><span class="sxs-lookup"><span data-stu-id="398ab-104">To reduce latency, the solution uses a local cache for the configuration values.</span></span> <span data-ttu-id="398ab-105">该解决方案在每隔五分钟刷新的缓存。</span><span class="sxs-lookup"><span data-stu-id="398ab-105">The solution refreshes the cache every five minutes.</span></span>  
  
 <span data-ttu-id="398ab-106">在许多应用程序中使用适配器来处理 SSO 操作，包括获取 SSO 票证，兑换票证，并使用的凭据来访问关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="398ab-106">In many applications, the adapters handle the SSO operations—including getting an SSO ticket, redeeming the ticket, and using the credentials to gain access to the affiliate application.</span></span> <span data-ttu-id="398ab-107">但是，面向服务的解决方案的内联版本不使用适配器。</span><span class="sxs-lookup"><span data-stu-id="398ab-107">However, the inline version of the service oriented solution does not use adapters.</span></span> <span data-ttu-id="398ab-108">它必须通过代码使用 SSO。</span><span class="sxs-lookup"><span data-stu-id="398ab-108">It must use SSO from code.</span></span>  
  
 <span data-ttu-id="398ab-109">本主题介绍该解决方案使用的缓存机制以及如何在解决方案的内联版本通过代码使用 SSO。</span><span class="sxs-lookup"><span data-stu-id="398ab-109">This topic describes the caching mechanism used by the solution, as well as how the inline version of the solution uses SSO from code.</span></span>  
  
## <a name="local-caching-of-configuration-values"></a><span data-ttu-id="398ab-110">本地缓存配置值</span><span class="sxs-lookup"><span data-stu-id="398ab-110">Local Caching of Configuration Values</span></span>  
 <span data-ttu-id="398ab-111">面向服务的解决方案使用两个对象， **ConfigPropertyBag**并**ConfigParameters**，目的是处理的配置值。</span><span class="sxs-lookup"><span data-stu-id="398ab-111">The service oriented solution uses two objects, **ConfigPropertyBag** and **ConfigParameters**, to handle the configuration values.</span></span> <span data-ttu-id="398ab-112">**ConfigPropertyBag**类保留的值和使用仅由**ConfigParameters**类。</span><span class="sxs-lookup"><span data-stu-id="398ab-112">The **ConfigPropertyBag** class holds the values and is used only by the **ConfigParameters** class.</span></span> <span data-ttu-id="398ab-113">**ConfigParameters**解决方案的其他部分使用类来检索配置参数。</span><span class="sxs-lookup"><span data-stu-id="398ab-113">The **ConfigParameters** class is used by the other parts of the solution to retrieve the configuration parameters.</span></span> <span data-ttu-id="398ab-114">这两个类均位于**Microsoft.Samples.BizTalk.WoodgroveBank.ConfigHelper**命名空间。</span><span class="sxs-lookup"><span data-stu-id="398ab-114">Both classes are in the **Microsoft.Samples.BizTalk.WoodgroveBank.ConfigHelper** namespace.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="398ab-115">面向服务的解决方案在 300 秒 （5 分钟） 修补程序缓存刷新间隔。</span><span class="sxs-lookup"><span data-stu-id="398ab-115">The Service Oriented solution fixes the cache refresh interval at 300 seconds (5 minutes).</span></span> <span data-ttu-id="398ab-116">相反，您可能希望在此解决方案中进行缓存刷新间隔本身的可配置属性。</span><span class="sxs-lookup"><span data-stu-id="398ab-116">You may, instead, want to make the cache refresh interval itself  a configurable property in this solution.</span></span> <span data-ttu-id="398ab-117">这是在业务流程管理解决方案。</span><span class="sxs-lookup"><span data-stu-id="398ab-117">This is done in the Business Process Management solution.</span></span> <span data-ttu-id="398ab-118">有关该解决方案如何处理 SSO 的详细信息，请参阅[业务流程管理解决方案中有效使用 SSO](../core/using-sso-efficiently-in-the-business-process-management-solution.md)。</span><span class="sxs-lookup"><span data-stu-id="398ab-118">For more information about how that solution handles SSO, see [Using SSO Efficiently in the Business Process Management Solution](../core/using-sso-efficiently-in-the-business-process-management-solution.md).</span></span> <span data-ttu-id="398ab-119">请注意，在这种情况下，刷新间隔中的更改才会生效之前的旧的间隔时间结束时刷新缓存。</span><span class="sxs-lookup"><span data-stu-id="398ab-119">Notice that, in such a case, a change in the refresh interval does not take effect until the cache is refreshed at the end of the old interval time.</span></span>  
  
 <span data-ttu-id="398ab-120">**ConfigPropertyBag**具有以下方法：</span><span class="sxs-lookup"><span data-stu-id="398ab-120">The **ConfigPropertyBag** has the following methods:</span></span>  
  
|<span data-ttu-id="398ab-121">方法</span><span class="sxs-lookup"><span data-stu-id="398ab-121">Method</span></span>|<span data-ttu-id="398ab-122">Description</span><span class="sxs-lookup"><span data-stu-id="398ab-122">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="398ab-123">读取</span><span class="sxs-lookup"><span data-stu-id="398ab-123">Read</span></span>|<span data-ttu-id="398ab-124">检索给定属性的值。</span><span class="sxs-lookup"><span data-stu-id="398ab-124">Retrieves a value for a given property.</span></span>|  
|<span data-ttu-id="398ab-125">写入</span><span class="sxs-lookup"><span data-stu-id="398ab-125">Write</span></span>|<span data-ttu-id="398ab-126">将值分配给一个属性。</span><span class="sxs-lookup"><span data-stu-id="398ab-126">Assigns a value to a property.</span></span>|  
  
 <span data-ttu-id="398ab-127">类使用.NET 的实例**NameValueCollection**以保存的值。</span><span class="sxs-lookup"><span data-stu-id="398ab-127">The class uses an instance of a .NET **NameValueCollection** to hold the values.</span></span> <span data-ttu-id="398ab-128">两个访问方法实现**IPropertyBag**从接口**Microsoft.BizTalk.SSOClient.Interop**命名空间。</span><span class="sxs-lookup"><span data-stu-id="398ab-128">The two access methods implement the **IPropertyBag** interface from the **Microsoft.BizTalk.SSOClient.Interop** namespace.</span></span> <span data-ttu-id="398ab-129">**ConfigPropertyBag**类是一个内部类，仅供**ConfigParameters**类。</span><span class="sxs-lookup"><span data-stu-id="398ab-129">The **ConfigPropertyBag** class is an internal class and used only by the **ConfigParameters** class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="398ab-130">属性包中的键名是不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="398ab-130">Key names in the property bag are case insensitive.</span></span> <span data-ttu-id="398ab-131">基础**NameValueCollection**使用不区分大小写的哈希算法和不区分大小写的比较。</span><span class="sxs-lookup"><span data-stu-id="398ab-131">The underlying **NameValueCollection** uses case-insensitive hashing and case-insensitive comparisons.</span></span>  
  
 <span data-ttu-id="398ab-132">应用程序使用**ConfigParameters**类来处理 SSO 配置值。</span><span class="sxs-lookup"><span data-stu-id="398ab-132">The application uses the **ConfigParameters** class to handle the SSO configuration values.</span></span> <span data-ttu-id="398ab-133">类具有以下公共方法和属性：</span><span class="sxs-lookup"><span data-stu-id="398ab-133">The class has the following public methods and attributes:</span></span>  
  
|<span data-ttu-id="398ab-134">方法或属性</span><span class="sxs-lookup"><span data-stu-id="398ab-134">Method or Attribute</span></span>|<span data-ttu-id="398ab-135">Description</span><span class="sxs-lookup"><span data-stu-id="398ab-135">Description</span></span>|  
|-------------------------|-----------------|  
|<span data-ttu-id="398ab-136">SSOConfigParameter</span><span class="sxs-lookup"><span data-stu-id="398ab-136">SSOConfigParameter</span></span>|<span data-ttu-id="398ab-137">用于指定配置参数的枚举。</span><span class="sxs-lookup"><span data-stu-id="398ab-137">An enumeration for specifying configuration parameters.</span></span>|  
|<span data-ttu-id="398ab-138">GetConfigParameters</span><span class="sxs-lookup"><span data-stu-id="398ab-138">GetConfigParameters</span></span>|<span data-ttu-id="398ab-139">用于检索给定参数的值的方法。</span><span class="sxs-lookup"><span data-stu-id="398ab-139">A method used to retrieve a value for a given parameter.</span></span> <span data-ttu-id="398ab-140">使用 SSOConfigParameter 来指示该参数。</span><span class="sxs-lookup"><span data-stu-id="398ab-140">Uses the SSOConfigParameter to indicate the parameter.</span></span>|  
  
 <span data-ttu-id="398ab-141">**ConfigParameters**类使用.NET Timer 类和一个委托函数来设置的刷新**ConfigPropertyBag**:</span><span class="sxs-lookup"><span data-stu-id="398ab-141">The **ConfigParameters** class uses the .NET Timer class and a delegate function to set up the refresh of the **ConfigPropertyBag**:</span></span>  
  
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
  
 <span data-ttu-id="398ab-142">请注意静态构造函数初始化静态成员变量，因此使用类方法而无需创建类的实例。</span><span class="sxs-lookup"><span data-stu-id="398ab-142">Notice that the static constructor initializes the static member variables thus enabling the use of class methods without creating an instance of the class.</span></span> <span data-ttu-id="398ab-143">该构造函数创建的 SSO 配置存储的实例 (**ISSOConfigStore**)，配置属性包 (**ConfigPropertyBag**)，以及同步锁 (**ReaderWriterLock**) 用来控制访问**ConfigurationPropertyBag**期间更新和读取。</span><span class="sxs-lookup"><span data-stu-id="398ab-143">The constructor creates instances of the SSO configuration store (**ISSOConfigStore**), the configuration property bag (**ConfigPropertyBag**), and a synchronization lock (**ReaderWriterLock**) used to control access to the **ConfigurationPropertyBag** during updates and reads.</span></span> <span data-ttu-id="398ab-144">然后，构造函数使用**GetConfigInfo**检索 SSO 配置值并将其放在属性包。</span><span class="sxs-lookup"><span data-stu-id="398ab-144">The constructor then uses **GetConfigInfo** to retrieve the SSO configuration values and to put them in the property bag.</span></span> <span data-ttu-id="398ab-145">最后，该构造函数创建**计时器**对象，它在指定间隔之后调用委托函数**cacheRefreshCallback**。</span><span class="sxs-lookup"><span data-stu-id="398ab-145">Finally, the constructor creates a **Timer** object that, after the specified interval, calls the delegate function, **cacheRefreshCallback**.</span></span>  
  
 <span data-ttu-id="398ab-146">**计时器**委托函数是相对来说比较简单：</span><span class="sxs-lookup"><span data-stu-id="398ab-146">The **Timer** delegate function is relatively straightforward:</span></span>  
  
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
  
 <span data-ttu-id="398ab-147">请注意，cacherefreshcallback 方法禁用该计时器，以便该方法可以一直运行。</span><span class="sxs-lookup"><span data-stu-id="398ab-147">Notice that the cache refresh callback method disables the timer so that the method can run all the way through.</span></span> <span data-ttu-id="398ab-148">另请注意使用锁来控制对属性包的访问。</span><span class="sxs-lookup"><span data-stu-id="398ab-148">Also notice the use of the locks to control access to the property bag.</span></span> <span data-ttu-id="398ab-149">**ReaderWriterLock**是最佳选择，它的适用的情况下有读取多于写入的。</span><span class="sxs-lookup"><span data-stu-id="398ab-149">The **ReaderWriterLock** is the best choice here—it is designed for cases where there are more reads than writes.</span></span> <span data-ttu-id="398ab-150">此外请注意，锁**syncLock**、 是静态的且在类级别的所有线程都共享同一个的单一实例，它的声明。</span><span class="sxs-lookup"><span data-stu-id="398ab-150">Notice also that the lock, **syncLock**, is static and declared at the class level that all threads share the same, single instance of it.</span></span>  
  
## <a name="using-sso-from-code"></a><span data-ttu-id="398ab-151">通过代码使用 SSO</span><span class="sxs-lookup"><span data-stu-id="398ab-151">Using SSO from Code</span></span>  
 <span data-ttu-id="398ab-152">当使用单一登录从代码时，代码必须承担适配器的角色:，即从消息中检索 SSO 票证，兑换票证以获取后端系统中，用户名和密码，并最后，使用后端系统。</span><span class="sxs-lookup"><span data-stu-id="398ab-152">When using single sign-on from code, the code must take on the role of the adapter: that is,retrieve the SSO ticket from the message, redeem the ticket to get the user name and password for the back-end system, and, finally, use the back-end system.</span></span> <span data-ttu-id="398ab-153">面向服务的解决方案执行此通过**GetPendingTransactionsResponse**方法**来**对象。</span><span class="sxs-lookup"><span data-stu-id="398ab-153">The service-oriented solution does this through the **GetPendingTransactionsResponse** method of the **PendingTransactionsCaller** object.</span></span>  
  
 <span data-ttu-id="398ab-154">此方法将出现，如下所示：</span><span class="sxs-lookup"><span data-stu-id="398ab-154">The method appears as follows:</span></span>  
  
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
  
 <span data-ttu-id="398ab-155">该方法首先检索配置信息，包括 URL 后, 端系统和后端 （关联） 应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="398ab-155">The method begins by retrieving configuration information, including the URL, for the back-end system and the name of the backend (affiliate) application.</span></span>  
  
 <span data-ttu-id="398ab-156">若要兑换票证，该方法必须票证和原始请求用户名从消息中提取。</span><span class="sxs-lookup"><span data-stu-id="398ab-156">To redeem the ticket, the method must extract the ticket and original requesting user name from the message.</span></span> <span data-ttu-id="398ab-157">消息作为消息上下文属性中的一个包含该票证**BTS。SSOTicket**。</span><span class="sxs-lookup"><span data-stu-id="398ab-157">The message contains the ticket as one of the message context properties, **BTS.SSOTicket**.</span></span> <span data-ttu-id="398ab-158">有关详细信息，请参阅**消息上下文属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="398ab-158">For more information, see **Message Context Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span> <span data-ttu-id="398ab-159">该方法还会提取**OriginatorSID**从消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="398ab-159">The method also extracts the **OriginatorSID** from the message context properties.</span></span> <span data-ttu-id="398ab-160">有了票证和原始发件人的名称后，该方法调用 RedeemTicket 方法以检索凭据的票证上。</span><span class="sxs-lookup"><span data-stu-id="398ab-160">With the ticket and the originator's name in hand, the method calls the RedeemTicket method on the ticket to retrieve the credentials.</span></span>  
  
 <span data-ttu-id="398ab-161">代码的其余部分创建一个.NET NetworkCredential 缓存的凭据，并调用后端 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="398ab-161">The remainder of the code creates a .NET NetworkCredential cache for the credentials and calls the back-end Web service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="398ab-162">用户名和密码从不恢复 SSO 以明文形式，因为你想要最大程度减少保存该信息的变量的生存期。</span><span class="sxs-lookup"><span data-stu-id="398ab-162">Because the user name and password come back from SSO in clear text, you want to minimize the lifetime of variables holding that information.</span></span> <span data-ttu-id="398ab-163">请注意，该代码声明凭据变量内的**尝试**块。</span><span class="sxs-lookup"><span data-stu-id="398ab-163">Notice that the code declares the credential variables within a **try** block.</span></span> <span data-ttu-id="398ab-164">变量在这里，在从退出时过期**尝试**块。</span><span class="sxs-lookup"><span data-stu-id="398ab-164">Here, the variables expire upon exit from the **try** block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="398ab-165">请参阅</span><span class="sxs-lookup"><span data-stu-id="398ab-165">See Also</span></span>  
 [<span data-ttu-id="398ab-166">面向服务的解决方案的实施要点</span><span class="sxs-lookup"><span data-stu-id="398ab-166">Implementation Highlights of the Service Oriented Solution</span></span>](../core/implementation-highlights-of-the-service-oriented-solution.md)