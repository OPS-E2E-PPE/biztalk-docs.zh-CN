---
title: 处理错误的错误 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 602be8a5-1f28-457d-8e12-ba06cff65491
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dafc64afb24ce8bb7995e7852a778b17a556f018
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240821"
---
# <a name="error-handling-errors"></a>处理错误时出错
用于诊断和解决 WCF 错误处理错误的信息。  

## <a name="error-handling-options-disable-location-on-failure-and-suspend-request-message-on-failure-should-not-both-be-set-to-false"></a>错误处理选项“失败时禁用位置”和“失败时挂起请求消息”不应同时设置为 False    
||详细信息|  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|事件 ID|0|  
|事件源|0|  
|组件|0|  
|符号名称|0|  
|消息正文|错误处理选项“失败时禁用位置”和“失败时挂起请求消息”不应都设置为 False，因为可能发生消息丢失。 请将一个或两个选项设置为 True。|  
  
## <a name="explanation"></a>解释  
 在 WCF NetMsmq 适配器选项中**禁用失败的位置**和**失败的挂起请求消息**不能二者都应该处于选中状态。 由于接收位置继续接收无效消息，但这些消息未被挂起并存储在 MessageBox 中，则可能发生消息丢失。  
  
## <a name="user-action"></a>用户操作  
 使用以下过程配置适配器设置。    

1. 打开 **“BizTalk Server 管理”**。  
  
2.  在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。  
  
3.  找到应用程序，然后找到您的传输。  
  
4.  右键单击传输名称。  
  
5.  选择**属性**。  
  
6.  在端口**类型**列表中，选择正确的端口。  
  
7.  选择 **“配置”**。  
  
8.  在**WCF [***传输类型***] 传输属性**对话框中，选择**消息**选项卡。  
  
9. 在**错误处理**部分中，确保或者**禁用失败的位置**或**失败的挂起请求消息**已选中。