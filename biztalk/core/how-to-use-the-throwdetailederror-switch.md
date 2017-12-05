---
title: "如何使用 ThrowDetailedError 交换机 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Web services, security
- Web services, debugging
ms.assetid: 8a8af3c0-a9a2-42fe-b0be-a5a106403747
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 90929015e2d1d0567af0ccc5c51c6aae450d49c8
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-use-the-throwdetailederror-switch"></a><span data-ttu-id="b0e01-102">如何使用 ThrowDetailedError 开关</span><span class="sxs-lookup"><span data-stu-id="b0e01-102">How to Use the ThrowDetailedError Switch</span></span>
<span data-ttu-id="b0e01-103">如果发生错误，Web 客户端接收泛型**SoapException**。</span><span class="sxs-lookup"><span data-stu-id="b0e01-103">If an error occurs, the Web client receives a generic **SoapException**.</span></span>  
  
 <span data-ttu-id="b0e01-104">若要调试已发布的 Web Services，您可以向 Web.config 文件添加一个开关来控制由已发布 Web Services 返回的异常详细信息的级别。</span><span class="sxs-lookup"><span data-stu-id="b0e01-104">To debug your published Web service, you can add a switch to the Web.config file to control the level of the exception details returned from the published Web service.</span></span>  
  
 <span data-ttu-id="b0e01-105">Web.config 文件包含应用程序设置交换机， **ThrowDetailedError**。</span><span class="sxs-lookup"><span data-stu-id="b0e01-105">The Web.config file contains an application setting switch, **ThrowDetailedError**.</span></span> <span data-ttu-id="b0e01-106">**False**是默认设置**ThrowDetailedError**。</span><span class="sxs-lookup"><span data-stu-id="b0e01-106">**False** is the default setting for **ThrowDetailedError**.</span></span> <span data-ttu-id="b0e01-107">如果你将设置更改为**True**，服务器代理将内部异常信息返回给使你能够调试已发布的 Web 服务的 Web 客户端。</span><span class="sxs-lookup"><span data-stu-id="b0e01-107">If you change the setting to **True**, the server proxy returns inner exception information to the Web client enabling you to debug the published Web service.</span></span>  
  
 <span data-ttu-id="b0e01-108">下面的 XML 代码演示**ThrowDetailedError**下 Web.config 文件中出现的交换机\<appSettings\>节点：</span><span class="sxs-lookup"><span data-stu-id="b0e01-108">The following XML code shows the **ThrowDetailedError** switch that appears in the Web.config file under the \<appSettings\> node:</span></span>  
  
```  
<appSettings>  
  <add key="ThrowDetailedError" value="False" />  
<appSettings/>  
```  
  
> [!IMPORTANT]
>  <span data-ttu-id="b0e01-109">默认情况下 BizTalk Server 不会将内部异常信息返回至 Web 客户端，因为该信息可能包含诸如应用程序调用堆栈之类的敏感信息。</span><span class="sxs-lookup"><span data-stu-id="b0e01-109">BizTalk Server does not return inner exception information to the Web client by default since it may contain sensitive information, such as application call stacks.</span></span> <span data-ttu-id="b0e01-110">调试后，应设置**ThrowDetailedError**将设置为**False**。</span><span class="sxs-lookup"><span data-stu-id="b0e01-110">After debugging, you should set the **ThrowDetailedError** setting to **False**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0e01-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b0e01-111">See Also</span></span>  
 [<span data-ttu-id="b0e01-112">调试已发布的 Web 服务</span><span class="sxs-lookup"><span data-stu-id="b0e01-112">Debugging Published Web Services</span></span>](../core/debugging-published-web-services.md)