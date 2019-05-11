---
title: 错误 Messages3 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- error messages
ms.assetid: 10ea12bb-eacb-477a-bc88-28f999e60a02
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 789bd5cdd12d14727320e50e6c8f9bc28f721333
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65347351"
---
# <a name="error-messages"></a>错误消息
下表列出了 PeopleSoft Enterprise 系统的组件接口及其描述，以及可能的更正方法中的错误消息。  
  
 **错误消息**  
  
|错误 ID|可能的原因 / 错误说明|可能的更正|  
|--------------|-----------------------------------------|-------------------------|  
|E-JNI0004|没有 psjoa.jar。<br /><br /> 出现 Java 异常。|验证 PeopleSoft psjoa.jar 文件的位置。|  
|E-PSFT0030|没有 psjoa.jar。<br /><br /> 实例化组件接口 Bean 失败。|验证 PeopleSoft psjoa.jar 文件的位置。|  
|E-PSFT0019|错误的服务器名称。<br /><br /> 无法连接到 PeopleSoft 应用程序服务器。|验证 PeopleSoft 主机和用户参数。|  
|E-PSFT0024|错误的用户名和密码。<br /><br /> 连接失败。 出现错误消息：JavaClient 是无效的用户名，或者您键入了错误的密码。|PeopleSoft 用户名和密码所需和区分大小写。 请确保在正确的大小和较低的情况下输入信息。|  
  
## <a name="see-also"></a>请参阅  
 [PeopleSoft 疑难解答](../core/troubleshooting-peoplesoft.md)