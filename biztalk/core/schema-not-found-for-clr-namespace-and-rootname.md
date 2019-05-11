---
title: 找不到 CLR Namespace 和 rootName 的架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: db283d81-1cb0-460d-ace4-49a91ceb4a02
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f4a854357a8f1e217273c1a3380a446dcbe7848
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396927"
---
# <a name="schema-not-found-for-clr-namespace-and-rootname"></a>找不到 CLR Namespace 和 rootName 的架构
## <a name="details"></a>详细信息  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                       EDI 引擎                                       |
|  符号名称  |                               SchemaNotFoundForCLRAndRN                                |
|  消息正文   |              找不到 CLR Namespace 架构 ={0}和 rootName = {1}               |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明接收管道找不到使用与交换关联的根名称和命名空间与已为交换解析的参与方相关联的文档架构。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保，从交换中获取的根名称和命名空间解析的参与方的属性从确定对应一起部署架构。 BizTalk 确定在文档类型和交换中的版本中的根名称。 BizTalk 确定在将架构从默认目标 Namespace 字段 （对于默认架构） 或"启用自定义事务集定义"网格 （适用于自定义架构） 中交换处理属性。