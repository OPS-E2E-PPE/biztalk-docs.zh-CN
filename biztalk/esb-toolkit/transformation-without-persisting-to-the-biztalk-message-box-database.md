---
title: 保持到 BizTalk 消息框中数据库的情况下转换 |Microsoft 文档
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
ms.openlocfilehash: 407725509121948619e4eb05b583f6c8c1362f9f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294981"
---
# <a name="transformation-without-persisting-to-the-biztalk-message-box-database"></a>保持到 BizTalk 消息框中数据库的情况下转换
在使用这种情况下，对 Web 服务的调用执行实时转换的一条消息，根据运行时的适当的映射的分辨率若要应用，并返回转换后的结果。 图 1 说明的过程的示意图。  
  
 ![保持的情况下转换](../esb-toolkit/media/ch3-transformationwithout.gif "Ch3 TransformationWithout")  
  
 **图 1**  
  
 **保持到 Microsoft BizTalk Server 消息框数据库的情况下转换消息**  
  
 包含转换服务示例[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]演示此用例。 通过使用它，您可以调用 ESB 转换服务;这使你可以在开发组件和 BizTalk Server 业务规则引擎中的策略时，测试转换和映射。  
  
 有关详细信息，请参阅[安装和运行转换服务示例](../esb-toolkit/installing-and-running-the-transformation-service-sample.md)。  
  
> [!NOTE]
>  不要混淆通过 BizTalk Server 转换代理执行的动态转换操作此处所称为转换服务。 转换服务是高性能 Web 服务，可通过直接调入 BizTalk Server 大幅减少延迟，而无需通过消息框数据库。