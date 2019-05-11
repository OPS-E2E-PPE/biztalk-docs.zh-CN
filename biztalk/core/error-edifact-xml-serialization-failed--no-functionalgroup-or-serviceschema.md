---
title: 由于结构无效，无 FunctionalGroup 或 ServiceSchema，Edifact 交换 Xml 序列化失败 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 530faadd-e301-4743-b4b3-b04ba7578f1d
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1e7b7f6c93203e3b4122c7f99ed5936df7ab0af
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388914"
---
# <a name="edifact-interchange-xml-serialization-failed-due-to-invalid-structure-no-functionalgroup-or-serviceschema"></a>由于结构无效，无 FunctionalGroup 或 ServiceSchema，Edifact 交换 Xml 序列化失败
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                              |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                              [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                              |
| 产品版本 |                                          [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                          |
|    事件 ID     |                                                                      -                                                                       |
|  事件源   |                            [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                            |
|    组件    |                                                                  EDI 引擎                                                                  |
|  符号名称  |                                                                      -                                                                       |
|  消息正文   | 由于结构无效，Edifact 交换 Xml 序列化失败。 查找 UNZ 的 FunctionalGroup 或 ServiceSchema，但没有找到。 |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明发送管道无法处理保留的 EDIFACT 批处理交换，因为该交换的 XML 文件中不包含 TransactionSetGroup 或 FunctionalGroup 标记。  
  
 当 BizTalk 处理保留的批处理交换时，为该交换的 XML 文件中的一组事务集或组给出了 XML 标记。 为一组组给出了 FunctionalGroup 标记。 ServiceSchema 标志表明用于保留的批处理交换的控制架构。 如果您使用接收管道和直通传输发送管道设置保留的批处理，则可能会出现此错误条件。 这些标记是由接收管道设置的并且由发送管道删除。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保为保留的批处理生成的 XML 文件具有格式正确的 XML 结构，该机构具有 FunctionalGroup 标记（对于多个组）和/或 ServiceSchema 标记（对于用于保留的批处理交换的控制架构）。