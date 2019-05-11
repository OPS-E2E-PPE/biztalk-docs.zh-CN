---
title: 受限字符范围 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e12213bf-750e-43a2-998a-949fa4255b73
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: add7cfdf529d21c7ed54ae60d1c39c39266af6fb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65255111"
---
# <a name="restricted-character-ranges"></a>受限的字符范围

## <a name="overview"></a>概述
创建平面文件消息架构时，你可以指示[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]来阻止特定字符或一系列在任何传出消息中包含的字符。 若要执行此操作，请在 BizTalk 编辑器中，打开要用作目标架构的架构。 选择**架构**节点，然后使用**受限字符**以打开**受限字符**对话框。 输入范围，你想要防止在 BizTalk Server 发送的任何消息中包含的字符，然后单击**确定**。 只要 BizTalk Server 尝试处理中指定的字符**受限字符**生成的目标架构，处理将停止一条错误消息的对话框。  

> [!NOTE]
>  在 BizTalk Server 中，字符范围限制是平面文件扩展的函数，在这种情况下，不适用于 XML 消息。 有关不同类型的消息可能在实现字符范围限制为其支持的消息格式的方式不同可能在将来提供的扩展。  

## <a name="see-also"></a>请参阅  
- [创建平面文件消息架构时的注意事项](../core/considerations-when-creating-flat-file-message-schemas.md)   
- **受限的字符 （平面文件架构的节点属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
