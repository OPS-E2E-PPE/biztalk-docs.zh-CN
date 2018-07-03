---
title: 文档规范类型找不到 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2cb2a458-d0f4-420d-8d35-0e739167464f
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46b8bffb132921e7b939f251db21e0c6c7839dc2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014222"
---
# <a name="document-spec-type-not-found"></a>找不到文档规格类型
## <a name="details"></a>详细信息  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                       EDI 引擎                                       |
|  符号名称  |                                           -                                            |
|  消息正文   |                            文档规范类型{0}找不到                            |
  
## <a name="explanation"></a>解释  
 此错误表明未找到架构。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请部署该文档架构：  
  
1.  启动**Microsoft Visual Studio**。  
  
2.  创建或打开现有项目  
  
3.  将架构添加到项目中。  
  
4.  在 Visual Studio 中部署项目。