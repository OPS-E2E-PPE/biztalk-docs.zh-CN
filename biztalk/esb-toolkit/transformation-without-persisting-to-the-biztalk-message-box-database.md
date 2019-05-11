---
title: 但不保存到 BizTalk Messagebox 数据库的转换 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7f5b4caf-88e9-41dd-a644-e229e411a4a7
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37f0b126a018f497add4b595ffb09d4eca1559a3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399620"
---
# <a name="transformation-without-persisting-to-the-biztalk-message-box-database"></a>转换不保留到 BizTalk Messagebox 数据库
在此用例，调用 Web 服务执行实时转换一条消息，根据运行时解析相应的映射的应用，并返回转换后的结果。 图 1 显示了该过程的示意图。  
  
 ![转换不保留](../esb-toolkit/media/ch3-transformationwithout.gif "Ch3-TransformationWithout")  
  
 **图 1**  
  
 **但不保存到 Microsoft BizTalk Server Messagebox 数据库中转换消息**  
  
 中包含的转换服务示例[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]演示此用例。 通过使用它，你可以调用 ESB 转换服务;这使您可以在你开发组件和 BizTalk Server 业务规则引擎中的策略测试转换和映射。  
  
 有关详细信息，请参阅[安装和运行转换服务示例](../esb-toolkit/installing-and-running-the-transformation-service-sample.md)。  
  
> [!NOTE]
>  不要混淆通过 BizTalk Server 转换代理执行的动态转换操作与此处所称为转换服务。 转换服务是直接调入 BizTalk Server 通过显著降低延迟，而无需通过 Messagebox 数据库的高性能 Web 服务。