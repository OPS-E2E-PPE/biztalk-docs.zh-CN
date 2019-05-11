---
title: 错误-写入 XML 类型 Blob 文件时出错 (&lt;file:---{0}&gt;)。 错误： {1} |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bb787db4-0919-4e1b-bfe1-ba0e19a08881
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f8917230d4209079ef6f581e2f747fc45aafc827
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388873"
---
# <a name="error---failure-writing-xml-type-blob-file-ltfile---0gt-error-1"></a>错误-写入 XML 类型 Blob 文件时出错 (&lt;file:---{0}&gt;)。 错误： {1}
**错误代码**  
  
 btm1062  
  
 **说明**  
  
 当映射器编译器不能在生成任务指定的位置中创建的 xml blob 文件时，将发生这种情况。  
  
 **用户执行任何操作**  
  
 检查包含在消息中的错误消息 (错误{1}) 我。 如果它是未经授权的异常，则可能不需要的项目输出文件夹的写入权限。