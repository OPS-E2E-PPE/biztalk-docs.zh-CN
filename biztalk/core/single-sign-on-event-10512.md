---
title: 单一登录： 事件 10512 |Microsoft Docs
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
ms.openlocfilehash: 54ba5a340a1a7590dae72016a3e747726ea68125
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980958"
---
# <a name="single-sign-on-event-10512"></a>单一登录： 事件 10512
## <a name="details"></a>详细信息  

|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  产品名称   |                 企业单一登录                  |
| 产品版本 | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    事件 ID     |                           10512                            |
|  事件源   |                           ENTSSO                           |
|    组件    |                            N\A                             |
|  符号名称  |                   SSO_ERROR_LOADLIBRARY                    |
|  消息正文   |      无法加载 %1%r<br /><br /> 错误代码: %2。       |

## <a name="explanation"></a>解释  
 此错误事件表明指定的动态链接库 (DLL) 无法加载到 SSO 服务器进程中。 如果 SSO 安装目录（通常为 C:\Program Files\Common Files\Enterprise Single Sign-On）中丢失 DLL，则可能表明未正确完成安装，或者在安装完成后删除了 DLL。 如果 DLL 存在，则 SSO 服务将正确路径解析到 DLL 时可能出现问题。 此外，DLL 本身也可能损坏。  

## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行下列一项或多项操作:  

- 如果怀疑出现更大范围的安装失败，则可能必须卸载并重新安装产品。  

- 如果一个 DLL 丢失或损坏，请尝试将其替换，然后重新启动服务。  

  有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：  

- [实现企业单一登录](../core/implementing-enterprise-single-sign-on.md)
