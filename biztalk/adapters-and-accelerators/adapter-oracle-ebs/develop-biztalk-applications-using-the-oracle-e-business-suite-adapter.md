---
title: 开发 BizTalk 应用程序使用 Oracle E-business Suite 适配器 |Microsoft Docs
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
ms.openlocfilehash: 2ecbd7fd418cdc686bcd8d0a49e2486e377fbd5c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375548"
---
# <a name="develop-biztalk-applications-using-the-oracle-e-business-suite-adapter"></a>开发 BizTalk 应用程序使用 Oracle E-business Suite 适配器
开发 BizTalk 应用程序涉及到创建的 BizTalk 项目中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，并使用 **[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]** 或 **[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]** 生成 XML 架构。 后生成架构后，你可以使用基于内容的路由 (CBR)，或创建 BizTalk 业务流程发送和接收符合你生成的架构的消息。  
  
 CBR 可以在发送到 Oracle E-business Suite 的消息不需要任何密集型处理方案中使用。 例如，如果您知道，只有特定类型的接收端口接收消息，您可以将筛选器添加到消息路由到发送端口的筛选器表达式匹配的发送端口。  

## <a name="use-orchestration"></a>使用业务流程  
 BizTalk 业务流程中创建发送和接收端口以发送和接收消息来回[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]，后者又将发送到消息[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 
 
 本部分提供有关使用 BizTalk 业务流程执行的任务和操作上使用 Oracle E-business Suite 的信息[!INCLUDE[adapteroraclebusinessshort_md](../../includes/adapteroraclebusinessshort-md.md)]。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]又使用[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]，这可以与 WCF 绑定进行交互。  
  
> [!IMPORTANT]
>  若要使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]与 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，你必须始终设置**EnableBizTalkCompatibilityMode**属性绑定到**True**。 有关步骤，请参阅[适用于 Oracle E-business Suite 中配置的绑定属性](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md)。  
  

  
## <a name="see-also"></a>请参阅  
[开发 Oracle E-business Suite 应用程序](../../adapters-and-accelerators/adapter-oracle-ebs/develop-your-oracle-e-business-suite-applications.md)