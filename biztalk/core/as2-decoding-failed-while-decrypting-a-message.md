---
title: 解密消息时，出现 AS2 解码失败 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ab6f7ecd-23cf-4f6f-8f63-acc6618dc544
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 78dea4d186de1b4cfe34998abc3f627eae0e8977
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528559"
---
# <a name="as2-decoding-failed-while-decrypting-a-message"></a>解密消息时，出现 AS2 解码失败
## <a name="details"></a>详细信息  

|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                       AS2 引擎                                       |
|  符号名称  |                                           -                                            |
|  消息正文   |                    在解密消息时，出现 AS2 解码失败。                     |

## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明接收管道的 AS2 解码器组件无法解密 AS2 消息。 如果解密过程中使用的证书无效、未存储在相应的位置或者与加密过程中使用的证书不匹配，都会发生此错误。  

## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行下列一项或多项操作:  

- 验证 AS2 消息中的加密包装是否有效。 如果无效，请确定编码器对消息编码不正确的原因。  

- 验证加密过程中使用的公钥和解密过程中使用的私钥是否匹配。  

- 验证用于加密和解密的证书的“密钥用法”属性是否设置为“数据加密”。  

- 验证是否没有断开的中间证书颁发机构链。 如果有，请删除旧证书，创建并使用新证书。  

- 通过检查证书存储区中的过期日期来验证该证书是否过时（使用具有证书管理单元的 MMC）。  

- 通过检查证书吊销列表来验证证书是否尚未被吊销。 （可以通过选中 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台“常规 AS2”属性的“检查证书吊销列表”属性，让 BizTalk Server 自动检查此项。）  

- 验证用于解密的证书是否存储在每台承载 MIME/SMIME 解码器管道的 BizTalk Server 上针对每个主机实例服务帐户的“当前用户\个人”存储区中。
