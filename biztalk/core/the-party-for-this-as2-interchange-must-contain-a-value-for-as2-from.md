---
title: 此 AS2 交换的参与方必须包含值为 AS2-从 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5d338759-5646-4dc2-8319-a42aaa8c3d9c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 637224e0519a181c71b12e390c39c821ad354ac6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009246"
---
# <a name="the-party-for-this-as2-interchange-must-contain-a-value-for-as2-from"></a>此 AS2 交换的参与方必须包含 AS2-From 的值
## <a name="details"></a>详细信息  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                       AS2 引擎                                       |
|  符号名称  |                              InvalidAgreementAS2FromName                               |
|  消息正文   |         此 AS2 交换的参与方必须包含 AS2-From 的值。          |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明发送管道无法发送 AS2 消息，因为没有为解析后的作为消息接收方的参与方设置 AS2-From 属性。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请打开 BizTalk Server 管理控制台，移动到“参与方”节点，打开为消息解析的参与方的“AS2 属性”对话框，单击“作为 AS2 消息接收方的参与方”节点，然后为“AS2-From”属性输入值。