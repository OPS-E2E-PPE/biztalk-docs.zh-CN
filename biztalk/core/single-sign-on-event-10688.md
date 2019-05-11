---
title: 单一登录：Event 10688 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 63fe4ac5-dc1d-4d5a-8ce3-40ed4556afcf
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e760441481a5eddfd2d7d53294a8f6f4abade8fb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397410"
---
# <a name="single-sign-on-event-10688"></a>单一登录：事件 10688
## <a name="details"></a>详细信息  

|                 |                                                                           |
|-----------------|---------------------------------------------------------------------------|
|  产品名称   |                         企业单一登录                         |
| 产品版本 |        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]         |
|    事件 ID     |                                   10688                                   |
|  事件源   |                                  ENTSSO                                   |
|    组件    |                                    N\A                                    |
|  符号名称  |                   SSO_ERROR_REPLAY_FILE_UNEXPECTED_DATA                   |
|  消息正文   | 在重播 file.%r 中检测到损坏。<br /><br /> 重播文件： %1 |

## <a name="explanation"></a>解释  
 此错误事件表示 SSO 已重建与 SSO 数据库的联系，但无法读取重播文件由于损坏问题。 如果 SSO 无法打开重播文件，它将继续进行到下一个重播文件 （如果有）。  

 ENTSSO 服务器无法与 SSO 数据库取得联系时，密码同步使用重播文件。 进度文件指示，距离通过 SSO 无法重播文件中用例联系人与 SSO 数据库会再次读取。  

## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下操作：  

- 检查有相关事件的系统和应用程序事件日志。  

- 删除重播文件。  

  有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：  

- [如何配置密码同步](../core/how-to-configure-password-synchronization.md)  

- [密码同步](../core/password-synchronization2.md)
