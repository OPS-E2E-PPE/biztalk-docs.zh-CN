---
title: 批处理支持为一个事务性接口接收适配器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5289e8b8-4447-4196-9f7c-5e60c6598d8d
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 27b51a67f63f3088ce64c9db35c368289ce156d2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257573"
---
# <a name="interfaces-for-a-transactional-batch-supported-receive-adapter"></a>批处理支持为一个事务性接口接收适配器
接收适配器可在要求消息的事务性提交时创建和控制事务。  
  
 一个事务性接收适配器创建，并将指针传递到 Microsoft 分布式事务处理协调器 (MSDTC) 事务**完成**方法**IBTTransportBatch**接口。 这确保所有批操作都在该特定事务对象的作用域中执行。 在批提交完成后，适配器回调方法将提交或回滚该事务。 它所采用的操作取决于从传输代理返回的状态，并且还可能取决于适配器执行的其他与事务相关的工作（而该工作对传输代理不可见）。 适配器将确定事务是失败还是成功。 适配器 （提交或回滚） 事务的结果回过来向报告传输代理使用**DTCCommitConfirm**方法**IBTDTCCommitConfirm**接口。 它将传递`true`成功事务或`false`失败。  
  
 下图显示在创建支持事务性批的接收适配器时的对象交互。  
  
 ![](../core/media/ebiz-sdk-devadapter2.gif "ebiz_sdk_devadapter2")  
接收适配器使用 DTC 事务提交一批消息的工作流  
  
## <a name="see-also"></a>另请参阅  
 [适配器变量](../core/adapter-variables.md)   
 [开发接收适配器](../core/developing-a-receive-adapter.md)   
 [实例化和初始化接收适配器](../core/instantiating-and-initializing-a-receive-adapter.md)   
 [进程内的接口接收适配器](../core/interfaces-for-an-in-process-receive-adapter.md)   
 [一个独立的接口接收适配器](../core/interfaces-for-an-isolated-receive-adapter.md)   
 [批处理支持的接口接收适配器](../core/interfaces-for-a-batch-supported-receive-adapter.md)   
 [接口同步请求-响应接收适配器](../core/interfaces-for-a-synchronous-request-response-receive-adapter.md)