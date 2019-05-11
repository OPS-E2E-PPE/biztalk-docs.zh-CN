---
title: 一个或多个段出错 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4ee86667-e72a-4f1b-8d5c-15ca710dbe5d
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 17af00eb0347a1654feafd59046596741829b9b0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65323410"
---
# <a name="one-or-more-segments-in-error"></a>有一个或多个段出错
## <a name="details"></a>详细信息  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                       EDI 引擎                                       |
|  符号名称  |                        X12TsOneOrMoreSegmentsInErrorDescription                        |
|  消息正文   |                             有一个或多个段出错                              |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明交换中的一个或多个段不符合管理它们的架构。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确定哪个段有错误，打开管理该段的架构，并通过该架构确定该段出错的原因。