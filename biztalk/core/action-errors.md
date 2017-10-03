---
title: "操作错误 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 87cf0a5b-d1dd-4807-9660-e8a8b7012b40
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 49f25f1f15307077943ef370a335885690bea22c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="action-errors"></a>操作错误
本部分包含有关诊断和解决 WCF 操作错误的详细信息。  
  
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|事件 ID|0|  
|事件源|0|  
|组件|0|  
|符号名称|0|  
|消息正文|单个操作不能包含换行符。 删除所有换行符。 或者，若要指定多个操作，请使用操作映射语法。|  
  
## <a name="explanation"></a>解释  
 此错误表示发送端口的操作属性包含换行符，这是不允许的。  
  
> [!NOTE]
>  当操作定义为映射时，不存在此限制。  
  
## <a name="user-action"></a>用户操作  
 使用以下过程来修复操作属性。  
  
 
1.  打开 **“BizTalk Server 管理”**。  
  
2.  在控制台根目录中，展开**BizTalk Server 管理**，展开**BizTalk 组**，然后展开**应用程序**。  
  
3.  找到您的应用程序，然后找到您的传输。  
  
4.  右键单击传输名称。  
  
5.  选择**属性**。  
  
6.  在端口**类型**列表中，选择正确的端口。  
  
7.  选择 **“配置”**。  
  
8.  在**WCF [***传输类型***] 传输属性**对话框中，选择**常规**选项卡。  
  
9. 在**SOAP 操作标头**部分中，删除中的新行字符**操作**文本框。  

## <a name="more-good-info"></a>良好的详细信息  
 有关操作的其他信息，请参阅[指定 WCF 发送适配器的 SOAP 操作](../core/specifying-soap-actions-for-wcf-send-adapters.md)