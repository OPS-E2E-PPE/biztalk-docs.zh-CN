---
title: 错误消息 1> |Microsoft 文档
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
ms.openlocfilehash: 80a44049c43c499ac05a8a6f296d11add934267a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="error-messages"></a>错误消息
下表介绍了 JD Edwards EnterpriseOne 系统中的错误消息，并提供了可能的更正。  
  
|错误 ID|可能的原因 / 错误说明|可能的更正|  
|--------------|-----------------------------------------|-------------------------|  
|E JDE0027|缺少 JD Edwards EnterpriseOne JAR。 无法获取 JD Edwards EnterpriseOne 连接对象。|验证您的凭据。 验证您的 CLASSPATH 设置和登录凭据。 环境变量引用。|  
|我 JDE0043|错误配置文件，用户，密码的应用程序服务器、 端口、 环境、 路径。 登录失败。|验证您的登录凭据。 环境变量引用。|  
|我 JDE0048|如果 jdearglist.txt 文件不存在或为空，当 JD Edwards EnterpriseOne 的 Microsoft BizTalk 适配器打开时，会在登录中显示信息性消息。|更新 jdearglist.txt 文件以输入参数的列表，以便它们会自动右对齐，并因此，在左侧空白填充。 有关详细信息，请参阅[处理字符串值](../core/handling-string-values2.md)。 每次更改 jdearglist，你必须重新生成该业务对象的架构。|  
|E JDE0027|无法获取 JD Edwards EnterpriseOne 连接对象。 请检查您的 CLASSPATH 和凭据。|验证 jdeinterop.ini 的位置。|  
  
## <a name="see-also"></a>另请参阅  
 [故障排除博士 Edwards EnterpriseOne](../core/troubleshooting-jd-edwards-enterpriseone.md)   
 [技术参考](../core/technical-reference6.md)