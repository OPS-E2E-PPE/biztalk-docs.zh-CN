---
title: 验证 AS2 消息时出错 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0cf97c63-2bff-4474-9cd8-f68634493dcc
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6b7d797989290b0211e619e0c5ae4b4408cda02c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360068"
---
# <a name="an-error-occurred-when-validating-an-as2-message"></a>验证 AS2 消息时出错
## <a name="details"></a>详细信息  

|                 |                                                                                                                       |
|-----------------|-----------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                   |
| 产品版本 |                              [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                               |
|    事件 ID     |                                                           -                                                           |
|  事件源   |                [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                 |
|    组件    |                                                      AS2 引擎                                                       |
|  符号名称  |                                                           -                                                           |
|  消息正文   | 验证 AS2 消息时出错。 请确保使用的证书不具有已超时或被吊销。 |

## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 AS2 接收管道或 AS2 发送管道无法验证 AS2 消息。 如果签名验证过程中使用的证书无效、 未存储在相应的位置，或与签名过程中使用的证书不匹配，这可能发生。  

## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行下列一项或多项操作:  

- 验证 AS2 消息中的签名包装有效。 如果没有，确定为什么消息错误签名的编码器。  

- 验证签名过程中使用的私钥和签名验证过程中使用的公钥匹配。  

- 验证用于签名和签名验证的证书的密钥用法属性设置为"数据加密"。  

- 验证是否没有断开的中间证书颁发机构链。 如果有，请删除旧证书，创建并使用新证书。  

- 通过检查证书存储区中的过期日期来验证该证书是否过时（使用具有证书管理单元的 MMC）。  

- 通过检查证书吊销列表来验证证书是否尚未被吊销。 （可以通过选中 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台“常规 AS2”属性的“检查证书吊销列表”属性，让 BizTalk Server 自动检查此项。）  

- 验证用于签名验证的证书存储在本地计算机 / 其他人将存储的每个 BizTalk server 承载 MIME/SMIME 解码器管道的每个主机实例服务帐户。
