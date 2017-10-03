---
title: "开发 Oracle E-business Suite 应用程序使用 WCF 通道模型 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 75bb6de1-e11a-4377-af13-e1cb954aaf3f
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e99dfa0c69500b86fe086ce0daa81e3ffb62857d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="develop-oracle-e-business-suite-applications-using-the-wcf-channel-model"></a>开发 Oracle E-business Suite 应用程序使用 WCF 通道模型
你可以使用[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]通道模型来使用[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]通过直接通过使用 Oracle EBS 绑定创建的通道实例发送 XML 消息。  
  
 通过使用的强类型类和 WCF 服务模型公开是通道模型提供更好地控制细化 Oracle E-business Suite 执行的操作的方法使用 WCF 通道模型的一个优点。 此控件来自在 WCF 通道模型中，你直接控制通过通道发送的消息的内容的事实。  
  
 在某些情况下，此额外级别是控制的有益的。 例如，当使用 WCF 通道模型来执行更新操作在表上的，你有选择地可以直接更新目标行中的列，通过省略消息中传递的更新模板中的列。 仅有的列所需那些带有"nillable = false"WSDL 中。 由公开的更新方法[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]客户端对于表架构中包含的每个列的模板使用强类型的记录参数。  
  
 本部分中的主题说明如何执行操作[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]使用 WCF 通道模型。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [与 Oracle E-business Suite 适配器的 WCF 通道模型概述](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-channel-model-with-the-oracle-e-business-suite-adapter.md)  
  
-   [创建一个通道，使用 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-channel-using-oracle-e-business-suite.md)
  
-   [在 Oracle E-business Suite 使用 WCF 通道模型运行接口表上的 insert 操作](../../adapters-and-accelerators/adapter-oracle-ebs/insert-on-an-interface-table-in-oracle-ebs-using-the-wcf-channel-model.md)  
  
-   [轮询 Oracle E-business Suite SELECT 语句中使用 WCF 通道模型](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-select-statement-with-the-wcf-channel-model.md)
  
## <a name="see-also"></a>另请参阅  
[开发 Oracle E-business Suite 应用程序](../../adapters-and-accelerators/adapter-oracle-ebs/develop-your-oracle-e-business-suite-applications.md)