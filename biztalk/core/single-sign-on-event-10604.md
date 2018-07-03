---
title: 单一登录： 事件 10604 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eea14ab1-5a89-4a62-b414-1bcb36ea339e
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 48996ec333c9035e57393e270db06ca173cfc9e6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990582"
---
# <a name="single-sign-on-event-10604"></a>单一登录： 事件 10604
## <a name="details"></a>详细信息  
  
|                 |                                                                                                          |
|-----------------|----------------------------------------------------------------------------------------------------------|
|  产品名称   |                                        企业单一登录                                         |
| 产品版本 |                        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                        |
|    事件 ID     |                                                  10604                                                   |
|  事件源   |                                                  ENTSSO                                                  |
|    组件    |                                                   N/A                                                    |
|  符号名称  |                                      SSO_ERROR_SSOCSTX_OUT_OF_PROC                                       |
|  消息正文   | ENTSSO Server COM + 应用程序配置不正确。 它必须是 COM + 库应用程序。 |
  
## <a name="explanation"></a>解释  
 COM + 应用程序必须配置为 COM + 库应用程序。  
  
## <a name="user-action"></a>用户操作  
 在 ENTSSO MMC 管理单元中，展开 COM+ 文件夹并找到您的 ENTSSO Server。 右键单击此服务器，然后单击“属性”。 选择“库应用程序”而不是“服务器应用程序”，然后单击“确定”。