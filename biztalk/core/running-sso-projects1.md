---
title: 运行 SSO Projects1 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SSO projects
- running SSO projects
- samples, SSO projects
ms.assetid: f8da1874-7495-47cd-a3a3-881f722c80a2
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 533baacb49f486620675bf50593844d995569202
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65254590"
---
# <a name="running-sso-projects"></a><span data-ttu-id="8b52d-102">运行 SSO 项目</span><span class="sxs-lookup"><span data-stu-id="8b52d-102">Running SSO Projects</span></span>
<span data-ttu-id="8b52d-103">可以从 Internet Explorer 运行示例。</span><span class="sxs-lookup"><span data-stu-id="8b52d-103">You can run the sample  from Internet Explorer.</span></span>  
  
## <a name="running-a-sample-from-internet-explorer"></a><span data-ttu-id="8b52d-104">从 Internet Explorer 运行示例</span><span class="sxs-lookup"><span data-stu-id="8b52d-104">Running a Sample from Internet Explorer</span></span>  
  
#### <a name="to-run-the-sample-from-the-internet-explorer"></a><span data-ttu-id="8b52d-105">若要从 Internet Explorer 运行示例</span><span class="sxs-lookup"><span data-stu-id="8b52d-105">To run the sample from the Internet Explorer</span></span>  
  
1. <span data-ttu-id="8b52d-106">打开浏览器。</span><span class="sxs-lookup"><span data-stu-id="8b52d-106">Open your browser.</span></span>  
  
2. <span data-ttu-id="8b52d-107">使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="8b52d-107">Use the following syntax:</span></span>  
  
   ```  
   http://localhost/SSODemo/BTSHTTPReceive.dll?[Insert XML Instance body]   
   ```  
  
    <span data-ttu-id="8b52d-108">例如：</span><span class="sxs-lookup"><span data-stu-id="8b52d-108">For example:</span></span>  
  
    <span data-ttu-id="8b52d-109">http://localhost/SSODemo/BTSHTTPReceive.dll?<ns0:method_list_method%20xmlns:ns0="http://microsoft.com/exposed/object/object1"><ns0:method_list_method><ns1:method_list%20xmlns:ns1="http://microsoft.com/exposed/object"><ns1:comp_code></ns1:comp_code><ns1:comp_name></ns1:comp_name></ns1:object_1></ns0:method_list></ns0:method_list_method></span><span class="sxs-lookup"><span data-stu-id="8b52d-109">http://localhost/SSODemo/BTSHTTPReceive.dll?<ns0:method_list_method%20xmlns:ns0="http://microsoft.com/exposed/object/object1"><ns0:method_list_method><ns1:method_list%20xmlns:ns1="http://microsoft.com/exposed/object"><ns1:comp_code></ns1:comp_code><ns1:comp_name></ns1:comp_name></ns1:object_1></ns0:method_list></ns0:method_list_method></span></span>  
  
    <span data-ttu-id="8b52d-110">在这种情况下不需要提供凭据。</span><span class="sxs-lookup"><span data-stu-id="8b52d-110">In this case you do not have to provide the credentials.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b52d-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="8b52d-111">See Also</span></span>  
 [<span data-ttu-id="8b52d-112">保护适配器</span><span class="sxs-lookup"><span data-stu-id="8b52d-112">Secure the adapter</span></span>](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)