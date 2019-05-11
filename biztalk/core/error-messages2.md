---
title: 错误 Messages2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- error messages, JD Edwards OneWorld adapters
- adapters [JD Edwards OneWorld adapters], error messages
- JD Edwards OneWorld adapters, error messages
ms.assetid: 9fb65d50-83c6-426e-a0d6-674800ecf70f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6de1d180bb0f44eac2af17eee03577ee4b45d70b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388603"
---
# <a name="error-messages"></a>错误消息
下表介绍 JD Edwards OneWorld 系统中的错误消息，并提供可能的更正。  
  
|错误 ID|可能的原因 / 错误说明|可能的更正|  
|--------------|-----------------------------------------|-------------------------|  
|**E-JDE0002**|缺少 JD Edwards OneWorld JAR 文件。<br /><br /> 未能实例化用于 JD Edwards OneWorld Java Data Bean 的类对象。|验证存储库的路径。<br /><br /> 有关详细信息，请参阅[基本类型](../core/basic-types1.md)。|  
|**E-JDE0027**|缺少 JD Edwards OneWorld JAR 文件。 无法获取 JD Edwards OneWorld 连接对象。|验证您的 CLASSPATH 环境变量。<br /><br /> 请参阅更新该 CLASSPATH。<br /><br /> 验证您的凭据。<br /><br /> 有关详细信息，请参阅[基本类型](../core/basic-types1.md)。|  
||缺少 JD Edwards OneWorld JAR 文件。<br /><br /> 存储库的路径不正确。|验证 jdeinterop.ini 的位置。 验证 jdeinterop.ini 文件中设置的存储库的路径。<br /><br /> 导入到另一台计算机的 JD Edwards OneWorld 业务流程时，必须手动复制 jdeinterop.ini。|  
||无法获取 JD Edwards OneWorld 连接对象。|验证您的 CLASSPATH 设置和登录凭据...|  
|**I-JDE0043**|错误配置文件中，用户，密码的应用程序服务器、 端口、 环境、 路径。<br /><br /> 登录失败。|验证您的登录凭据。<br /><br /> 有关详细信息，请参阅[基本类型](../core/basic-types1.md)。|  
|**I-JDE0048**|如果 jdearglist.txt 文件不存在或为空，当用于 JD Edwards OneWorld 的 Microsoft BizTalk 适配器打开时在日志中会显示一条信息性消息。|更新 jdearglist.txt 文件输入的参数的列表，使它们自动右对齐和填充在左边空白区域。<br /><br /> 请参阅[处理字符串值](../core/handling-string-values1.md)。<br /><br /> 每次更改 jdearglist 时，必须重新生成该业务对象的架构。|  
  
## <a name="see-also"></a>请参阅  
 [附录 a:数据类型](../core/appendix-a-data-types.md)   
 [JD Edwards OneWorld 疑难解答](../core/troubleshooting-jd-edwards-oneworld.md)