---
title: 单一登录：Event 10512 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4edf0512-112d-40b8-9e29-7dd67f999b6d
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf29293c12a566a82835510e07f23e52ba0ba243
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243388"
---
# <a name="single-sign-on-event-10512"></a>单一登录：事件 10512
## <a name="details"></a>详细信息  

|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  产品名称   |                 企业单一登录                  |
| 产品版本 | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    事件 ID     |                           10512                            |
|  事件源   |                           ENTSSO                           |
|    组件    |                            N\A                             |
|  符号名称  |                   SSO_ERROR_LOADLIBRARY                    |
|  消息正文   |      未能加载 %1 %r<br /><br /> 错误代码: %2。       |

## <a name="explanation"></a>解释  
 此错误事件表示不可能将指定的动态链接库 (DLL) 加载到 SSO 服务器进程。 如果 DLL 缺少在 SSO 安装目录中，通常 C:\Program Files\Common Files\Enterprise Single Sign-on，则可能表示未正确，完成安装程序，或在安装完成后删除了 DLL 已完成。 如果 DLL 存在，则可能会存在 SSO 服务将正确路径解析到 DLL 的问题。 此外，DLL 本身也可能损坏。  

## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行下列一项或多项操作:  

- 如果更广的故障可能有必要，卸载并重新安装该产品怀疑安装程序。  

- 如果单个 DLL 已丢失或损坏，尝试将其替换为，然后重新启动该服务。  

  有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：  

- [实现企业单一登录](../core/implementing-enterprise-single-sign-on.md)
