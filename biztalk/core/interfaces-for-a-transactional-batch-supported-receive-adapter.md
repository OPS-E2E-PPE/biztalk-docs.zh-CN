---
title: 接收适配器的接口的事务性批处理支持 |Microsoft Docs
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
ms.openlocfilehash: f46c7662fac5010c4f1effe56016fe2f5c5d5e8f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65331558"
---
# <a name="interfaces-for-a-transactional-batch-supported-receive-adapter"></a>接收适配器的接口的事务性批处理支持
一个接收适配器创建和所需的消息的事务性提交时，控制事务。  
  
 事务性接收适配器创建并将指针传递到 Microsoft 分布式事务处理协调器 (MSDTC) 的事务**完成**方法**IBTTransportBatch**接口。 这可确保在该特定事务对象的作用域中执行所有批处理操作的。 中的批提交完成后，适配器回调方法将提交或回滚事务。 所需的操作取决于状态返回从传输代理，并且可能在其他与事务相关的工作时适配器执行看不到传输代理。 适配器可以确定事务是失败还是成功。 适配器事务 （commit 或 rollback） 的结果返回到传输代理通过报告**DTCCommitConfirm**方法**IBTDTCCommitConfirm**接口。 它将传入`true`对于成功的事务或`false`失败。  
  
 下图显示了接收适配器创建事务的支持批的涉及到的对象交互。  
  
 ![](../core/media/ebiz-sdk-devadapter2.gif "ebiz_sdk_devadapter2")  
接收适配器提交一批消息使用 DTC 事务的工作流  
  
## <a name="see-also"></a>请参阅  
 [适配器变量](../core/adapter-variables.md)   
 [开发接收适配器](../core/developing-a-receive-adapter.md)   
 [实例化和初始化接收适配器](../core/instantiating-and-initializing-a-receive-adapter.md)   
 [接收适配器的进程内的接口](../core/interfaces-for-an-in-process-receive-adapter.md)   
 [接口独立接收适配器](../core/interfaces-for-an-isolated-receive-adapter.md)   
 [接收适配器的支持批的接口](../core/interfaces-for-a-batch-supported-receive-adapter.md)   
 [同步请求-响应接收适配器的接口](../core/interfaces-for-a-synchronous-request-response-receive-adapter.md)