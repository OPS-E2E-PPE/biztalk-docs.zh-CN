---
title: 开发 Oracle E-business Suite 应用程序使用 WCF 通道模型 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 75bb6de1-e11a-4377-af13-e1cb954aaf3f
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a50e2f8ad108f056dda89328ae2c680cce708956
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375562"
---
# <a name="develop-oracle-e-business-suite-applications-using-the-wcf-channel-model"></a>开发 Oracle E-business Suite 应用程序使用 WCF 通道模型
可以使用[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]通道模型使用[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]通过直接通过使用 Oracle EBS 绑定创建通道实例发送 XML 消息。  
  
 通过使用强类型化类和方法，WCF 服务模型公开是通道模型提供了对 Oracle E-business Suite 执行的操作的更精细地控制使用 WCF 通道模型的一个优点。 此控件的来源的事实，在 WCF 通道模型中，您可以直接控制在通道上发送的消息的内容。  
  
 在某些情况下，此额外级别的控制可能有益。 例如时使用的 WCF 通道模型以执行更新操作的表，将有选择地可以忽略传入的消息更新模板中的列，从而更新目标行中的列。 仅有的列所需的那些带有"nillable = false"的 WSDL 中。 公开的更新方法[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]客户端对于包括表架构中的每个列的模板使用强类型的记录参数。  
  
 在本部分中的主题介绍如何执行操作上[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]使用 WCF 通道模型。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [使用 Oracle E-business Suite 适配器的 WCF 通道模型概述](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-channel-model-with-the-oracle-e-business-suite-adapter.md)  
  
-   [创建一个通道，使用 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-channel-using-oracle-e-business-suite.md)
  
-   [Oracle E-business Suite 使用 WCF 通道模型中运行插入操作在界面表](../../adapters-and-accelerators/adapter-oracle-ebs/insert-on-an-interface-table-in-oracle-ebs-using-the-wcf-channel-model.md)  
  
-   [SELECT 语句中使用 WCF 通道模型轮询 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-select-statement-with-the-wcf-channel-model.md)
  
## <a name="see-also"></a>请参阅  
[开发 Oracle E-business Suite 应用程序](../../adapters-and-accelerators/adapter-oracle-ebs/develop-your-oracle-e-business-suite-applications.md)