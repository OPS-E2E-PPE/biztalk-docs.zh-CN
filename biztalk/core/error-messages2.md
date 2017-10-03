---
title: "错误 Messages2 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- error messages, JD Edwards OneWorld adapters
- adapters [JD Edwards OneWorld adapters], error messages
- JD Edwards OneWorld adapters, error messages
ms.assetid: 9fb65d50-83c6-426e-a0d6-674800ecf70f
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 84b26891592162c553fb270d2d8c9482f1c2b4d9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="error-messages"></a>错误消息
下表介绍的是 JD Edwards OneWorld 系统中的错误消息，并为其提供可用的更正。  
  
|错误 ID|可能的原因 / 错误说明|可能的更正|  
|--------------|-----------------------------------------|-------------------------|  
|**E JDE0002**|JD Edwards OneWorld JAR 文件丢失<br /><br /> 无法实例化 JD Edwards OneWorld Java Data Bean 的类对象。|验证存储库的路径。<br /><br /> 有关详细信息，请参阅[基本类型](../core/basic-types1.md)。|  
|**E JDE0027**|JD Edwards OneWorld JAR 文件丢失 无法获取 JD Edwards OneWorld 连接对象。|验证您的 CLASSPATH 环境变量。<br /><br /> 请参阅更新该 CLASSPATH。<br /><br /> 验证您的凭据。<br /><br /> 有关详细信息，请参阅[基本类型](../core/basic-types1.md)。|  
||JD Edwards OneWorld JAR 文件丢失<br /><br /> 存储库的错误路径。|验证 jdeinterop.ini 的位置。 请验证在 jdeinterop.ini 文件中设置的存储库的路径。<br /><br /> 当将 JD Edwards OneWorld 业务流程导入到另一台计算机中时，您必须手动复制 jdeinterop.ini。|  
||无法获取 JD Edwards OneWorld 连接对象。|验证你的类路径设置和登录凭据...|  
|**我 JDE0043**|错误配置文件，用户，密码的应用程序服务器、 端口、 环境、 路径。<br /><br /> 登录失败。|验证你的登录凭据。<br /><br /> 有关详细信息，请参阅[基本类型](../core/basic-types1.md)。|  
|**我 JDE0048**|如果 jdearglist.txt 文件不存在或为空，当 JD Edwards OneWorld 的 Microsoft BizTalk 适配器打开时，信息性消息将出现在日志中。|更新 jdearglist.txt 文件以输入参数的列表，以便它们会自动右对齐，并因此，在左侧空白填充。<br /><br /> 请参阅[处理字符串值](../core/handling-string-values1.md)。<br /><br /> 每次更改 jdearglist，你必须重新生成该业务对象的架构。|  
  
## <a name="see-also"></a>另请参阅  
 [附录 a： 数据类型](../core/appendix-a-data-types.md)   
 [故障排除博士 Edwards OneWorld](../core/troubleshooting-jd-edwards-oneworld.md)