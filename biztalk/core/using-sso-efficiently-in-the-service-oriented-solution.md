---
title: "在服务中有效地使用 SSO 面向解决方案 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SSO, service solutions
- service solution tutorial, SSO
- SSO, using from code
ms.assetid: 809e0ad3-cc7f-4095-87d1-63031675a47f
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 66dafba56bdeedb8c7b35b4442623f55e70f1305
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-sso-efficiently-in-the-service-oriented-solution"></a>在服务中有效地使用 SSO 面向解决方案
面向服务的解决方案使用企业单一登录 (SSO) 来存储配置值和处理后端系统的凭据。 为缩短延迟时间，该解决方案使用本地缓存来存储配置值。 该解决方案每隔五分钟刷新一次缓存。  
  
 在许多应用程序中，都使用适配器来处理 SSO 操作，包括获取 SSO 票证，兑换票证，以及使用凭据来获取对关联应用程序的访问。 但是，面向服务的解决方案的内联版本不使用适配器。 它必须通过代码使用 SSO。  
  
 本主题介绍了该解决方案所使用的缓存机制，以及该解决方案的内联版本如何通过代码使用 SSO。  
  
## <a name="local-caching-of-configuration-values"></a>本地缓存的配置值  
 面向服务解决方案使用两个对象， **ConfigPropertyBag**和**ConfigParameters**，目的是处理的配置值。 **ConfigPropertyBag**类保持值，并仅供**ConfigParameters**类。 **ConfigParameters**解决方案的其他部分使用类来检索的配置参数。 这两个类位于**Microsoft.Samples.BizTalk.WoodgroveBank.ConfigHelper**命名空间。  
  
> [!NOTE]
>  面向服务的解决方案将缓存刷新间隔固定为 300 秒（5 分钟）。 当然，您可能希望将缓存刷新间隔本身作为该解决方案中的一个可配置的属性。 在业务流程管理解决方案中就是这么做的。 有关该解决方案如何处理 SSO 的详细信息，请参阅[业务流程管理解决方案中有效使用 SSO](../core/using-sso-efficiently-in-the-business-process-management-solution.md)。 请注意，在这种情况下，对刷新间隔所做的更改直到在原有间隔结束时发生的刷新缓存之后才会生效。  
  
 **ConfigPropertyBag**具有以下方法：  
  
|方法|Description|  
|------------|-----------------|  
|读取|检索给定属性的值。|  
|写入|为属性赋值。|  
  
 类使用的.NET 实例**NameValueCollection**以保存的值。 两种访问方法实现**IPropertyBag**接口从**Microsoft.BizTalk.SSOClient.Interop**命名空间。 **ConfigPropertyBag**类是一个内部的类，仅供**ConfigParameters**类。  
  
> [!NOTE]
>  属性包中的键名不区分大小写。 基础**NameValueCollection**使用不区分大小写的哈希算法和不区分大小写的比较。  
  
 应用程序使用**ConfigParameters**类用于处理的 SSO 配置值。 这个类具有以下公共方法和属性：  
  
|方法或属性|Description|  
|-------------------------|-----------------|  
|SSOConfigParameter|用于指定配置参数的枚举。|  
|GetConfigParameters|用于检索给定参数值的方法。 使用 SSOConfigParameter 来指示该参数。|  
  
 **ConfigParameters**类使用.NET 计时器类和委托函数来设置的刷新**ConfigPropertyBag**:  
  
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
  
 请注意，静态构造函数初始化的是静态成员变量，因此即使不创建类实例也可以使用类方法。 此构造函数创建的 SSO 配置存储区的实例 (**ISSOConfigStore**)，配置属性包 (**ConfigPropertyBag**)，和的同步锁定 (**ReaderWriterLock**) 用于控制对访问**ConfigurationPropertyBag**期间更新和读取。 然后，此构造函数使用**GetConfigInfo**检索 SSO 配置值并将它们放在属性包。 最后，此构造函数创建**计时器**对象，指定的时间间隔之后, 将调用委托函数， **cacheRefreshCallback**。  
  
 **计时器**委托函数是相对比较简单：  
  
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
  
 请注意，cacheRefreshCallback 方法会禁用该计时器，以便该方法可以全程运行。 还要注意在控制对属性包的访问时锁的使用。 **ReaderWriterLock**是最佳选择 — 它的适用情况下在有多个读取超过写入。 此外请注意，该锁， **syncLock**、 是静态的在类级别所有线程都共享相同的单个实例，它的声明。  
  
## <a name="using-sso-from-code"></a>通过代码使用 SSO  
 在使用代码中的单一登录时，该代码必须执行适配器的作用： 即，从消息中检索 SSO 票证、 兑换票证，以获取用户名和密码对于后端系统中，并在最后，使用后端系统。 面向服务的解决方案执行此通过**GetPendingTransactionsResponse**方法**PendingTransactionsCaller**对象。  
  
 该方法如下所示：  
  
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
  
 该方法首先检索后端系统的配置信息（包括 URL）以及后端（关联）应用程序的名称。  
  
 为了兑换票证，该方法必须从消息中提取票证和原始请求用户名。 消息包含作为消息上下文属性中的一个票证**BTS。SSOTicket**。 有关详细信息，请参阅**消息上下文属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。 该方法还提取**OriginatorSID**从消息上下文属性。 有了票证和创建者名称后，该方法将对票证调用 RedeemTicket 方法以检索凭据。  
  
 其余的代码将为凭据创建一个 .NET NetworkCredential 缓存，并调用后端 Web Services。  
  
> [!NOTE]
>  由于用户名和密码是以明文形式从 SSO 中返回的，因此应最大限度地缩短保存该信息的变量的生存期。 请注意此代码声明中的凭据变量**重**块。 此处，变量退出之后都过期**重**块。  
  
## <a name="see-also"></a>另请参阅  
 [服务实现重点介绍面向解决方案](../core/implementation-highlights-of-the-service-oriented-solution.md)