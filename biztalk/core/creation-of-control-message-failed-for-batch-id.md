---
title: 创建控制消息失败，批次 id |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f03078e7-46b0-4082-9d66-6b892152a12d
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ba63bc570ac29f95c70b5bc6e09050e26c435b2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979798"
---
# <a name="creation-of-control-message-failed-for-batch-id"></a>创建控件消息失败，批 ID 为
## <a name="details"></a>详细信息  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                       EDI 引擎                                       |
|  符号名称  |                               CreateControlMessageFailed                               |
|  消息正文   |                  创建控制消息失败，批次 id {0}。                  |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 BizTalk Server 已启动/停止某个批处理。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保所包含协议的“协议”属性中存在具有给定 ID 的批处理并且数据库正在运行。