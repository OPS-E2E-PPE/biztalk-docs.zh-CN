---
title: 已知问题的 POP3 适配器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b6d621a2-4801-44fe-a266-d4c05ac82633
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4bc86b2ae14b04b160f7387f870615116e659b3f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22261941"
---
# <a name="known-issues-with-the-pop3-adapter"></a>POP3 适配器已知问题
本部分包含可帮助你避免出现错误的信息。  
  
## <a name="known-issues"></a>已知问题  
  
#### <a name="the-pop3-adapter-fails-to-process-documents-when-running-on-a-64-bit-operating-system"></a>POP3 适配器在运行在 64 位操作系统上时无法处理文档  
  
##### <a name="problem"></a>问题  
 POP3 适配器在运行在 64 位操作系统上时将无法处理文档。  
  
##### <a name="cause"></a>原因  
 POP3 适配器的适配器处理程序无法运行在 64 位主机实例上。  
  
##### <a name="resolution"></a>解决方法  
 如果要在 64 位计算机上运行 POP3 适配器，需要将 POP3 适配器处理程序配置为在 32 位主机中运行。 在可通过 BizTalk 管理控制台访问的“主机属性”页上提供了此选项。  
  
## <a name="see-also"></a>另请参阅  
 [故障排除 POP3 适配器](../core/troubleshooting-the-pop3-adapter.md)