---
title: 用例在平面文件架构中的处理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9f2b56d2-03fa-41e9-ae28-3275b404d4db
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4103b9f133ffac16b967832325effefba04b5ab2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357601"
---
# <a name="case-handling-in-flat-file-schemas"></a>在平面文件架构中处理的用例

## <a name="overview"></a>概述
可以使用**用例**属性时要执行的平面文件数据的大小写转换消息翻译为其等效的 XML 格式。 当平面文件组装器将 XML 消息转换为其等效的平面文件格式，并**用例**属性设置为**所有字母都大写**或**小写**，所有数据受相应架构将转换为大写或小写，分别将在翻译过程。  
  
 当**用例**属性设置为 **（默认）**，不执行任何大小写转换。  
  
## <a name="see-also"></a>请参阅  
 **考虑事项时创建平面文件消息架构**和**用例 （平面文件架构的节点属性）** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]