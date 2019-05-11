---
title: 如何使用 ThrowDetailedError 开关 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Web services, security
- Web services, debugging
ms.assetid: 8a8af3c0-a9a2-42fe-b0be-a5a106403747
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 160bf585d23ad366d04e9b897c66d45ef8be6bda
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333184"
---
# <a name="how-to-use-the-throwdetailederror-switch"></a><span data-ttu-id="bf364-102">如何使用 ThrowDetailedError 开关</span><span class="sxs-lookup"><span data-stu-id="bf364-102">How to Use the ThrowDetailedError Switch</span></span>
<span data-ttu-id="bf364-103">如果发生错误，Web 客户端会收到一个一般**SoapException**。</span><span class="sxs-lookup"><span data-stu-id="bf364-103">If an error occurs, the Web client receives a generic **SoapException**.</span></span>  
  
 <span data-ttu-id="bf364-104">若要调试已发布的 Web 服务，可以向 Web.config 文件以控制从已发布的 Web 服务返回的异常详细信息级别添加一个开关。</span><span class="sxs-lookup"><span data-stu-id="bf364-104">To debug your published Web service, you can add a switch to the Web.config file to control the level of the exception details returned from the published Web service.</span></span>  
  
 <span data-ttu-id="bf364-105">Web.config 文件包含应用程序设置开关**ThrowDetailedError**。</span><span class="sxs-lookup"><span data-stu-id="bf364-105">The Web.config file contains an application setting switch, **ThrowDetailedError**.</span></span> <span data-ttu-id="bf364-106">**False**是默认设置**ThrowDetailedError**。</span><span class="sxs-lookup"><span data-stu-id="bf364-106">**False** is the default setting for **ThrowDetailedError**.</span></span> <span data-ttu-id="bf364-107">如果您将设置更改为 **，则返回 True**，服务器代理将内部异常信息返回至 Web 客户端，从而可以调试已发布的 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="bf364-107">If you change the setting to **True**, the server proxy returns inner exception information to the Web client enabling you to debug the published Web service.</span></span>  
  
 <span data-ttu-id="bf364-108">下面的 XML 代码演示**ThrowDetailedError**下的 Web.config 文件中出现的交换机\<appSettings\>节点：</span><span class="sxs-lookup"><span data-stu-id="bf364-108">The following XML code shows the **ThrowDetailedError** switch that appears in the Web.config file under the \<appSettings\> node:</span></span>  
  
```  
<appSettings>  
  <add key="ThrowDetailedError" value="False" />  
<appSettings/>  
```  
  
> [!IMPORTANT]
>  <span data-ttu-id="bf364-109">BizTalk Server 不会不内部异常信息返回到 Web 客户端默认情况下由于它可能包含敏感信息，如应用程序调用堆栈。</span><span class="sxs-lookup"><span data-stu-id="bf364-109">BizTalk Server does not return inner exception information to the Web client by default since it may contain sensitive information, such as application call stacks.</span></span> <span data-ttu-id="bf364-110">调试后，应设置**ThrowDetailedError**将设置为**False**。</span><span class="sxs-lookup"><span data-stu-id="bf364-110">After debugging, you should set the **ThrowDetailedError** setting to **False**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf364-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="bf364-111">See Also</span></span>  
 [<span data-ttu-id="bf364-112">调试已发布的 Web 服务</span><span class="sxs-lookup"><span data-stu-id="bf364-112">Debugging Published Web Services</span></span>](../core/debugging-published-web-services.md)