---
title: 开发使用 Oracle E-business Suite 适配器的 BizTalk 应用程序 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bf3374a2-2fca-4df4-a1b1-d11cdc05d393
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d201987490d9395b07d043c67fa50a31400fe7cd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215029"
---
# <a name="develop-biztalk-applications-using-the-oracle-e-business-suite-adapter"></a>开发使用 Oracle E-business Suite 适配器的 BizTalk 应用程序
开发 BizTalk 应用程序涉及到创建中的 BizTalk 项目[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，并使用 **[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]** 或 **[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]** 生成 XML 架构。 一旦你已生成架构，你可以使用基于内容的路由 (CBR)，或创建 BizTalk 业务流程，以发送和接收符合您生成架构的消息。  
  
 CBR 可以用于的方案发送到 Oracle E-business Suite 的消息不需要任何密集型处理。 例如，如果你知道，某一类型的仅接收端口接收消息，你可以将筛选器添加到筛选器与表达式匹配的对发送端口将消息路由到发送端口。  

## <a name="use-orchestration"></a>使用业务流程  
 在 BizTalk 业务流程中创建发送和接收端口发送和接收消息，并从[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]，这反过来将消息发送到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 
 
 本部分提供有关使用 BizTalk 业务流程执行的任务以及使用 Oracle E-business Suite 操作的信息[!INCLUDE[adapteroraclebusinessshort_md](../../includes/adapteroraclebusinessshort-md.md)]。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]反过来使用[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]，这可以与的 WCF 绑定进行交互。  
  
> [!IMPORTANT]
>  若要使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]与 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，始终必须设置**EnableBizTalkCompatibilityMode**属性绑定到**True**。 有关步骤，请参阅[为 Oracle E-business Suite 配置的绑定属性](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md)。  
  

  
## <a name="see-also"></a>另请参阅  
[开发 Oracle E-business Suite 应用程序](../../adapters-and-accelerators/adapter-oracle-ebs/develop-your-oracle-e-business-suite-applications.md)