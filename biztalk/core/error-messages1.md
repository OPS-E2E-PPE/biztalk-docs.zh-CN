---
title: 错误消息 1> |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- error messages
ms.assetid: db9c9634-3f4b-4b38-b3ba-388e587fccd8
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 98c6c3f8e6b4e648d8f40add23ec45bb3821579f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65347397"
---
# <a name="error-messages"></a>错误消息
下表介绍 JD Edwards EnterpriseOne 系统中的错误消息，并提供可能的更正。  
  
|错误 ID|可能的原因 / 错误说明|可能的更正|  
|--------------|-----------------------------------------|-------------------------|  
|E-JDE0027|缺少 JD Edwards EnterpriseOne JAR 文件。 无法获取 JD Edwards EnterpriseOne 连接对象。|验证您的凭据。 验证您的 CLASSPATH 设置和登录凭据。 引用环境变量。|  
|I-JDE0043|错误配置文件中，用户，密码的应用程序服务器、 端口、 环境、 路径。 登录失败。|验证您的登录凭据。 引用环境变量。|  
|I-JDE0048|如果 jdearglist.txt 文件不存在或为空，当用于 JD Edwards EnterpriseOne 的 Microsoft BizTalk 适配器打开时在日志中会显示一条信息性消息。|更新 jdearglist.txt 文件输入的参数的列表，使它们自动右对齐和填充在左边空白区域。 有关详细信息，请参阅[处理字符串值](../core/handling-string-values2.md)。 每次更改 jdearglist 时，必须重新生成该业务对象的架构。|  
|E-JDE0027|无法获取 JD Edwards EnterpriseOne 连接对象。 请检查您的 CLASSPATH 和凭据。|验证 jdeinterop.ini 的位置。|  
  
## <a name="see-also"></a>请参阅  
 [JD Edwards EnterpriseOne 疑难解答](../core/troubleshooting-jd-edwards-enterpriseone.md)   
 [技术参考](../core/technical-reference6.md)