---
title: 使用 POP3 适配器的已知问题 |Microsoft Docs
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
ms.openlocfilehash: 78e978ed5be5fa556411566d35aa6fcf58c09fec
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380737"
---
# <a name="known-issues-with-the-pop3-adapter"></a>POP3 适配器已知问题
本部分包含可能帮助您避免错误的信息。  
  
## <a name="known-issues"></a>已知问题  
  
#### <a name="the-pop3-adapter-fails-to-process-documents-when-running-on-a-64-bit-operating-system"></a>POP3 适配器无法处理文档，在 64 位操作系统上运行时  
  
##### <a name="problem"></a>问题  
 在 64 位操作系统上运行时，POP3 适配器将不处理文档。  
  
##### <a name="cause"></a>原因  
 POP3 适配器的适配器处理程序无法在 64 位主机实例中运行。  
  
##### <a name="resolution"></a>解决方法  
 如果在 64 位计算机上正在运行 POP3 适配器，配置 POP3 适配器处理程序，在 32 位主机中运行。 此选项才可从 BizTalk 管理控制台访问的主机属性页上可用。  
  
## <a name="see-also"></a>请参阅  
 [POP3 适配器故障排除](../core/troubleshooting-the-pop3-adapter.md)