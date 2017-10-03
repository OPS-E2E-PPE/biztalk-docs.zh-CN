---
title: "什么 &#39; BizTalk Accelerator for HL7 中的新增功能 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- what's new
- BizTalk Accelerator for HL7, what's new
- getting started, what's new
ms.assetid: e98595a1-2d1e-488e-8a97-7cd561948b3b
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c350ef616acf61cab7910c5381cca02d68c919f5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="what39s-new-in-biztalk-accelerator-for-hl7"></a>什么 &#39; BizTalk Accelerator for HL7 中的新增功能
更改和更新与[!INCLUDE[HL7_CurrentVersion_FirstRef_md](../../includes/hl7-currentversion-firstref-md.md)]。 

## <a name="biztalk-server-2016"></a>BizTalk Server 2016

|功能|Description|  
|---|---| 
| **启动了到 LOB 连接** | 使用 MLLP 适配器，[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]可以启动或发起远程的业务线服务器 (LOB) 系统的连接。 LOB 等待连接，，然后将消息发送到[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]使用 MLLP 适配器。 有 MLLP 中的某些新属性接收配置此选项的位置。 请参阅： <br/><ul><li>[端到端教程中的步骤 4](../../adapters-and-accelerators/accelerator-hl7/step-4-create-receive-port-to-accept-adt^a03-messages-from-adt-using-mllp.md)</li><li>[步骤 4 中 interrogative 教程](../../adapters-and-accelerators/accelerator-hl7/step-4-create-the-receive-port-for-accepting-adt-query-messages.md)</li><li>[Interrogative 教程中的步骤 5](../../adapters-and-accelerators/accelerator-hl7/step-5-create-the-receive-port-for-accepting-his-messages.md)</li><li>[在批处理教程步骤 4](../../adapters-and-accelerators/accelerator-hl7/step-4-create-a-receive-port-for-accepting-the-batch-message.md)</li></ul>在[!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)]，较旧版本，HL7 MLLP 收到适配器等待远程的 LOB 服务器，以连接到 MLLP 适配器，并且 LOB 然后发送消息。 <br/><br/>请参阅[BTAHL7 将消息的路由](../../adapters-and-accelerators/accelerator-hl7/how-btahl7-routes-messages.md)有关详细信息。|

## <a name="biztalk-server-2013-r2"></a>BizTalk Server 2013 R2  
  
|功能|Description|  
|-------------|-----------------|  
|**64 位支持**|MLLP 适配器和 HL7 管道可以在两个 32 位和 64 位主机实例中运行。<br /><br /> [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]安装包括 32 位安装包和 64 位安装包。 在 32 位计算机上，仅安装 32 位包。 在 64 位计算机上安装 32 位**或**64 位包。 <br/><br/>**重要说明：**若要使用 64 位支持，仅安装 64 位包。 64 位包使适配器和管道在 32 位和 64 位模式下都能运行。|  
|**v2.6 以上架构支持**|支持包括：<br /><br /> -   **BTAHL7V26Common**项目： 包括 v2.6 以上架构。<br />-   **BTAHL7Common**项目： 包含 v2.6 以上架构和 ACK_26_GLO_DEF 确认架构; 用于生成针对 v2.6 以上消息的确认。<br />-   **MSH_25_GLO_DEF**架构： 句柄新消息包含 v2.6 以上架构并继续支持所有 v2 的标头字段。*x*架构。|  
|**动态 MLLP 适配器支持**|属性可以在运行时使用的单向或双向 （请求-响应） 配置了适配器发送端口。 请参阅[动态 MLLP 适配器](../../adapters-and-accelerators/accelerator-hl7/dynamic-mllp-adapter.md)。|  
|**"FreeText"支持**|如果字段或线段定义为"FreeText"，未能将分析字段/段中的字符数据。 请参阅[编码字符使用普通](../../adapters-and-accelerators/accelerator-hl7/encoding-characters-using-free-text.md)。|  
|**ACK 或 NACK 发送具有无效的 MSH 消息**|使用**ReturnErrorForInvalidMSH3**注册表项，将否定确认 (NACK) 发送到方如果将发生以下情况：<br /><br /> -无效 MSH3 （方不定义在 HL7 配置资源管理器） <br />    **AND**<br />-消息中的 MSH15 和 MSH16 值为 null 或为空<br /><br /> 若要发送 NACK，将以下注册表项设置为 1，然后重新启动主机实例：<br /><br /> 32 位主机：`HKLM\SOFTWARE\Microsoft\BizTalk Accelerator for HL7`<br /><br /> 64 位主机：`HKLM\ SOFTWARE\Wow6432Node\Microsoft\BizTalk Accelerator for HL7` <br/><br/>**提示：**端口可以订阅失败消息： <ul><li>使用**BTAHL7Schemas.ParseError = True**筛选条件。</li><li>使用**传递**管道。</li></ul>|  
|**ACK 消息实例保持活动**|如果有上游系统连接失败，确认 (ACK) 发送到上游系统仍然处于活动状态。<br /><br /> 新行为： 如果有上游系统连接失败，则挂起 ACK 消息。|  
|**不会发送\<SB >**|此属性添加到接收适配器端口配置属性。 若要启用此属性，设置**UseMLLPTransACK**值：<br /><br /> -当设置为**False** （默认值），如果以开始数据适配器发送消息\<SB >。 例如，发送以下消息：<br /> `<SB\>DataData<CR\>DataData<CR\>…`<br/><br />-当设置为**True**，该适配器将消息发送的数据是否丢失\<SB > 开始。 例如，发送以下消息：<br /> `DataData<CR\>DataData<CR\>…` <br/><br/>**重要说明：**了两个方式发送端口是否**不发送\<SB >**设置为 True，则它不会发送 SB 并显示消息到下游的系统。 同时，它可与下游系统中缺少 SB 接收确认。|  
|**接受缺少\<SB >**|此属性添加到发送适配器端口配置属性。 若要启用此属性，设置**UseMLLPTransACK**值：<br /><br /> -当设置为**False** （默认值），如果数据丢失了适配器返回错误\<SB > 开始。 例如，以下消息将返回错误：<br /> `DataData<CR\>DataData<CR\>…`<br/><br />-当设置为**True**，适配器可以接收消息，如果数据丢失了\<SB > 开始。 例如，收到以下消息：<br /> `<SB\>DataData<CR\>DataData<CR\>…` <br />`DataData<CR\>DataData<CR\>…` <br/><br/>**重要说明：**了两个方式接收端口是否**接受缺少\<SB >**设置为 True，则它将接受来自上游系统的消息中缺少 SB。 在同一时间它不会发送 SB 到上游系统。|  
  
## <a name="biztalk-server-2013"></a>BizTalk Server 2013  
  
 以前版本中包含以下增强功能：  
  
-   可恢复的批处理中批处理出方案 HL7 管道中的交换支持。  
  
 已在以前的版本中删除以下功能：  
  
-   从 BizTalk Server 中删除运行状况活动跟踪功能并因此从 BTAHL7 删除审核功能，但日志记录保持不变。  
  
 在早期版本中修改了以下功能：  
  
-   "审核和日志记录服务"会重命名为"HL7 日志记录服务"。  

## <a name="see-also"></a>另请参阅

[BizTalk Server 2016 的新增功能](../../install-and-config-guides/what-s-new-in-biztalk-server-2016.md)  
[什么是 BizTalk Server 2013 R2 和 2013年中的新增功能](../../install-and-config-guides/what-s-new-in-biztalk-server-2013-and-2013-r2.md)