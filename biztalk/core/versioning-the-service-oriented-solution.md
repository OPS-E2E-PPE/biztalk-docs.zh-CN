---
title: 版本控制服务面向解决方案 |Microsoft 文档
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
ms.openlocfilehash: af1c5d1475fc37322be9a8483963bbfd1432fbb4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287637"
---
# <a name="versioning-the-service-oriented-solution"></a>版本控制服务面向解决方案
充当前端到解决方案中，两个业务流程**CustomerServiceReceiveSend**和**CustomerServiceNativeRequestResponse**，调用中部、 工作业务流程的**CustomerService**。 业务流程调用取决于包含该业务流程的程序集的版本号。 由于所有三个业务流程都位于同一个程序集中，因此不存在版本控制问题。  
  
 此外，业务流程所实现的业务程序是寿命非常短的请求-响应过程，该过程会很快完成。 因此，在此解决方案中不会出现业务程序的版本控制问题，这是因为在不同版本的不同程序集中不存在不同的业务流程。  
  
 但是，业务流程要使用架构程序集中的架构。 如果对架构进行了修订并将其编译为不同的版本，则必须使用更新版本的架构程序集重新编译业务流程。  
  
## <a name="see-also"></a>另请参阅  
 [面向开发的服务解决方案](../core/developing-a-service-oriented-solution.md)