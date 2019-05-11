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
# <a name="running-sso-projects"></a>运行 SSO 项目
可以从 Internet Explorer 运行示例。  
  
## <a name="running-a-sample-from-internet-explorer"></a>从 Internet Explorer 运行示例  
  
#### <a name="to-run-the-sample-from-the-internet-explorer"></a>若要从 Internet Explorer 运行示例  
  
1. 打开浏览器。  
  
2. 使用以下语法：  
  
   ```  
   http://localhost/SSODemo/BTSHTTPReceive.dll?[Insert XML Instance body]   
   ```  
  
    例如：  
  
    http://localhost/SSODemo/BTSHTTPReceive.dll?<ns0:method_list_method%20xmlns:ns0="http://microsoft.com/exposed/object/object1"><ns0:method_list_method><ns1:method_list%20xmlns:ns1="http://microsoft.com/exposed/object"><ns1:comp_code></ns1:comp_code><ns1:comp_name></ns1:comp_name></ns1:object_1></ns0:method_list></ns0:method_list_method>  
  
    在这种情况下不需要提供凭据。  
  
## <a name="see-also"></a>请参阅  
 [保护适配器](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)