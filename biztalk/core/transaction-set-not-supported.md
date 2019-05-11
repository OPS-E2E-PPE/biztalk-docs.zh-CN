---
title: 不支持事务集 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5ffe8528-f34f-4189-8ee6-4ae1afb50c92
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 908705bf733e7f95f771520ce9adee5a70dfe330
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279789"
---
# <a name="transaction-set-not-supported"></a>不支持事务集
## <a name="details"></a>详细信息  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                       EDI 引擎                                       |
|  符号名称  |                              X12TsNotSupportedDescription                              |
|  消息正文   |                             不支持事务集                              |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明接收管道无法处理传入的交换，因为尚为该事务集的文档类型部署文档架构。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中为事务集的文档类型部署文档架构。