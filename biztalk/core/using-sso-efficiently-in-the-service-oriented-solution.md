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
# <a name="using-sso-efficiently-in-the-service-oriented-solution"></a>在服务中有效使用 SSO 面向解决方案
面向服务的解决方案使用企业单一登录 (SSO) 来存储配置值并处理后端系统的凭据。 若要减少延迟，解决方案时，可使用本地缓存来存储配置值。 该解决方案在每隔五分钟刷新的缓存。  
  
 在许多应用程序中使用适配器来处理 SSO 操作，包括获取 SSO 票证，兑换票证，并使用的凭据来访问关联应用程序。 但是，面向服务的解决方案的内联版本不使用适配器。 它必须通过代码使用 SSO。  
  
 本主题介绍该解决方案使用的缓存机制以及如何在解决方案的内联版本通过代码使用 SSO。  
  
## <a name="local-caching-of-configuration-values"></a>本地缓存配置值  
 面向服务的解决方案使用两个对象， **ConfigPropertyBag**并**ConfigParameters**，目的是处理的配置值。 **ConfigPropertyBag**类保留的值和使用仅由**ConfigParameters**类。 **ConfigParameters**解决方案的其他部分使用类来检索配置参数。 这两个类均位于**Microsoft.Samples.BizTalk.WoodgroveBank.ConfigHelper**命名空间。  
  
> [!NOTE]
>  面向服务的解决方案在 300 秒 （5 分钟） 修补程序缓存刷新间隔。 相反，您可能希望在此解决方案中进行缓存刷新间隔本身的可配置属性。 这是在业务流程管理解决方案。 有关该解决方案如何处理 SSO 的详细信息，请参阅[业务流程管理解决方案中有效使用 SSO](../core/using-sso-efficiently-in-the-business-process-management-solution.md)。 请注意，在这种情况下，刷新间隔中的更改才会生效之前的旧的间隔时间结束时刷新缓存。  
  
 **ConfigPropertyBag**具有以下方法：  
  
|方法|Description|  
|------------|-----------------|  
|读取|检索给定属性的值。|  
|写入|将值分配给一个属性。|  
  
 类使用.NET 的实例**NameValueCollection**以保存的值。 两个访问方法实现**IPropertyBag**从接口**Microsoft.BizTalk.SSOClient.Interop**命名空间。 **ConfigPropertyBag**类是一个内部类，仅供**ConfigParameters**类。  
  
> [!NOTE]
>  属性包中的键名是不区分大小写。 基础**NameValueCollection**使用不区分大小写的哈希算法和不区分大小写的比较。  
  
 应用程序使用**ConfigParameters**类来处理 SSO 配置值。 类具有以下公共方法和属性：  
  
|方法或属性|Description|  
|-------------------------|-----------------|  
|SSOConfigParameter|用于指定配置参数的枚举。|  
|GetConfigParameters|用于检索给定参数的值的方法。 使用 SSOConfigParameter 来指示该参数。|  
  
 **ConfigParameters**类使用.NET Timer 类和一个委托函数来设置的刷新**ConfigPropertyBag**:  
  
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
  
 请注意静态构造函数初始化静态成员变量，因此使用类方法而无需创建类的实例。 该构造函数创建的 SSO 配置存储的实例 (**ISSOConfigStore**)，配置属性包 (**ConfigPropertyBag**)，以及同步锁 (**ReaderWriterLock**) 用来控制访问**ConfigurationPropertyBag**期间更新和读取。 然后，构造函数使用**GetConfigInfo**检索 SSO 配置值并将其放在属性包。 最后，该构造函数创建**计时器**对象，它在指定间隔之后调用委托函数**cacheRefreshCallback**。  
  
 **计时器**委托函数是相对来说比较简单：  
  
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
  
 请注意，cacherefreshcallback 方法禁用该计时器，以便该方法可以一直运行。 另请注意使用锁来控制对属性包的访问。 **ReaderWriterLock**是最佳选择，它的适用的情况下有读取多于写入的。 此外请注意，锁**syncLock**、 是静态的且在类级别的所有线程都共享同一个的单一实例，它的声明。  
  
## <a name="using-sso-from-code"></a>通过代码使用 SSO  
 当使用单一登录从代码时，代码必须承担适配器的角色:，即从消息中检索 SSO 票证，兑换票证以获取后端系统中，用户名和密码，并最后，使用后端系统。 面向服务的解决方案执行此通过**GetPendingTransactionsResponse**方法**来**对象。  
  
 此方法将出现，如下所示：  
  
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
  
 该方法首先检索配置信息，包括 URL 后, 端系统和后端 （关联） 应用程序的名称。  
  
 若要兑换票证，该方法必须票证和原始请求用户名从消息中提取。 消息作为消息上下文属性中的一个包含该票证**BTS。SSOTicket**。 有关详细信息，请参阅**消息上下文属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。 该方法还会提取**OriginatorSID**从消息上下文属性。 有了票证和原始发件人的名称后，该方法调用 RedeemTicket 方法以检索凭据的票证上。  
  
 代码的其余部分创建一个.NET NetworkCredential 缓存的凭据，并调用后端 Web 服务。  
  
> [!NOTE]
>  用户名和密码从不恢复 SSO 以明文形式，因为你想要最大程度减少保存该信息的变量的生存期。 请注意，该代码声明凭据变量内的**尝试**块。 变量在这里，在从退出时过期**尝试**块。  
  
## <a name="see-also"></a>请参阅  
 [面向服务的解决方案的实施要点](../core/implementation-highlights-of-the-service-oriented-solution.md)