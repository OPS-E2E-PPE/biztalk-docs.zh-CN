---
title: "配置回退信封属性 （X12 事务集设置） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2a951f70-07d5-4a58-b1ea-e7117a45c545
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7aa7898d1e1a83da879400a89d5cd089ef2d4069
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-fallback-envelope-properties-x12-transaction-set-settings"></a>配置回退信封属性（X 12 事务集设置）
在**包络线**页**事务设置设置**部分中，你定义 BizTalk Server 如何生成它将发送到方的 X12 编码交换的 GS 段。 GS 段为 X12 编码的交换标识和指定功能组。  
  
> [!NOTE]
>  本主题还适用于与 HIPAA 相关的设置。  
  
## <a name="prerequisites"></a>先决条件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  
  
### <a name="to-define-the-gs-segments"></a>定义 GS 段  
  
1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**方**节点，，然后单击**X12 回退设置**。  
  
2.  在**X12 回退设置**对话框中，在**X12 协议页**选项卡上，在**事务设置设置**部分中，单击**包络线**.  
  
3.  有关**功能代码 (GS01)**，从下拉列表中选择一个值。  
  
4.  有关**应用程序发件人 (GS02)**，输入一个字母数字值，该值最少包含 2，最多 15 个。 这是必填字段。  
  
5.  有关**应用程序接收方 (GS03)**，输入一个字母数字值，该值最少包含 2，最多 15 个。 这是必填字段。  
  
6.  有关**日期格式 (GS04)**，从下拉列表中选择 CCYYMMDD 或 YYMMDD。 这是必填字段。  
  
7.  有关**时间格式 (GS05)**，从下拉列表中选择 HHMM、 HHMMSS 或 HHMMSSdd。 这是必填字段。  
  
8.  有关**责任代理 (GS07)**，从下拉列表中选择值。  
  
9. 有关**文档标识符 (GS08)**，输入一个字母数字值，该值最小为 1，最大为 12。 此字段为可选字段。  
  
10. 单击**应用**接受所做的更改，然后才能继续进行配置，或单击**确定**验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>另请参阅  
 [配置 X12 事务的回退协议属性设置](../core/configuring-x12-fallback-agreement-properties-for-transaction-set-settings.md)