---
title: 版本控制服务面向解决方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- versioning, service solutions
- service solution tutorial, versioning
ms.assetid: 0e09720f-53f2-4b38-aae3-a79ddfd35be5
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 34896f02ac6335c8f5041ca959b25fe9ab2716c3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393738"
---
# <a name="versioning-the-service-oriented-solution"></a>版本控制服务面向解决方案
充当前端到解决方案中，两个业务流程**CustomerServiceReceiveSend**并**CustomerServiceNativeRequestResponse**，中间的工作业务流程调用**CustomerService**。 业务流程调用取决于包含该业务流程的程序集的版本号。 由于所有三个业务流程是在同一程序集中，没有任何版本控制问题。  
  
 此外，实现的业务流程的业务流程是一个快速完成的生存期很短的请求-响应过程。 因此，版本控制的业务流程的问题不会出现在此解决方案中，有不同的业务流程中使用不同版本的不同程序集。  
  
 但是，业务流程执行操作中的架构程序集使用的架构。 如果架构进行了修订，并且编译为不同的版本，则必须重新编译了架构程序集的较新版本的业务流程。  
  
## <a name="see-also"></a>请参阅  
 [开发面向服务的解决方案](../core/developing-a-service-oriented-solution.md)