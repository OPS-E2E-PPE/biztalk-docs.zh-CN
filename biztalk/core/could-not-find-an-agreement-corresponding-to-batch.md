---
title: 找不到与批相对应的协议 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4d1c0480-9a6f-481a-9143-e5a55707c3b5
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b51fabd7aaf01d751f1a5ecff3c3a4e773e0b7b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978374"
---
# <a name="could-not-find-an-agreement-corresponding-to-batch"></a>找不到对应于批的协议
## <a name="details"></a>详细信息  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                       EDI 引擎                                       |
|  符号名称  |                               AgreementNotFoundForBatch                                |
|  消息正文   |                找不到与批相对应的协议{0}。                 |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 BizTalk Server 找不到对应于此 Id 尝试一批，若要启动/停止批处理或处理批处理消息。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保具有给定 Id 的批处理是包含协议的协议属性中存在。