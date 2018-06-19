---
title: '若要启用状态报告、 运行和 #39;BizTalk Server 配置 &#39;和配置 EDI AS2 状态报告功能 |Microsoft 文档'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bf125919-80ab-4cb8-b1f5-0f2616cc6f5c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 334e77ed58d460aea3ca37f73c1165d62da0f10b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268909"
---
# <a name="to-enable-status-reporting-run-39biztalk-server-configuration39-and-configure-edi-as2-status-reporting-feature"></a>若要启用状态报告、 运行和 #39;BizTalk Server 配置 &#39;和配置 EDI AS2 状态报告功能
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|EDI 引擎|  
|符号名称|0|  
|消息正文|若要启用状态报告，请运行“BizTalk Server 配置”并配置 EDI/AS2 状态报告功能。 |  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件指示，EDI/AS2 状态报告为不工作，因为尚未配置。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下操作：  
  
1.  运行 BizTalk 服务器配置向导。 单击 BizTalk EDI/AS2 运行时节点中，然后选中"启用 BizTalk EDI/AS2 运行时状态报告为此 BizTalk 组"属性。 你必须配置 BAM，以便配置 EDI/AS2 状态报告。  
  
2.  在 BizTalk Server 管理控制台中，启用 EDI 状态报告为方通过单击 EDI 属性对话框中的常规页中的"激活 EDI 报表"属性。 启用 AS2 状态报告为方通过单击 AS2 属性对话框中的常规页中的"激活 AS2 报表"属性。 启用 EDI 或 AS2 状态报告后，必须重新启动 BizTalk 服务。