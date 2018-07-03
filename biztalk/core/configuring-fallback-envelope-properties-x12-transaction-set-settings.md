---
title: 配置回退信封属性 （X12-事务集设置） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2a951f70-07d5-4a58-b1ea-e7117a45c545
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6225a931a991d4b4fb85a23525c53fe01f9e52db
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37021370"
---
# <a name="configuring-fallback-envelope-properties-x12-transaction-set-settings"></a>配置回退信封属性（X 12 事务集设置）
在中**信封**页**事务集设置**部分中，可以定义 BizTalk Server 如何生成它发送到参与方的 X12 编码交换的 GS 段。 GS 段为 X12 编码的交换标识和指定功能组。  
  
> [!NOTE]
>  本主题还适用于与 HIPAA 相关的设置。  
  
## <a name="prerequisites"></a>必要條件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  
  
### <a name="to-define-the-gs-segments"></a>定义 GS 段  
  
1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**方**节点，，然后单击**X12 后备设置**。  
  
2. 在中**X12 后备设置**对话框中**X12 协议页**选项卡上，在**事务集设置**部分中，单击**信封**.  
  
3. 有关**功能代码 (GS01)**，从下拉列表中选择一个值。  
  
4. 有关**应用程序发送方 (GS02)**，输入最小为 2、 最大为 15 的字母数字值。 这是必填字段。  
  
5. 有关**应用程序接收方 (GS03)**，输入最小为 2、 最大为 15 的字母数字值。 这是必填字段。  
  
6. 有关**日期格式 (GS04)**，从下拉列表中选择 CCYYMMDD 或 YYMMDD。 这是必填字段。  
  
7. 有关**时间格式 (GS05)**，从下拉列表中选择 HHMM、 HHMMSS 或 HHMMSSdd。 这是必填字段。  
  
8. 有关**责任代理 (GS07)**，从下拉列表中选择值。  
  
9. 有关**文档标识符 (GS08)**，输入最小为 1 和最大为 12 的字母数字值。 此字段为可选字段。  
  
10. 单击**Apply**以接受更改，然后才能继续进行配置，或单击**确定**以验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>请参阅  
 [为事务集设置配置 X12 后备协议属性](../core/configuring-x12-fallback-agreement-properties-for-transaction-set-settings.md)