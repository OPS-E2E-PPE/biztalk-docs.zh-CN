---
title: 使用位置记录解析平面文件架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components [custom], flat file documents
- pipeline components [custom], parsing
ms.assetid: 1ceb8c06-ac21-490e-b3d5-54e5035e5f6a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4e7b816e345fde33a29515333f4498d6ab744043
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395071"
---
# <a name="parsing-flat-file-schemas-with-positional-records"></a>使用位置记录解析平面文件架构
当解析带有大小不等的位置记录的平面文件架构，必须包括在每个架构记录或尾部，以指示每个位置记录的大小中的标记。 否则，解析引擎返回的最长的记录大小。  
  
## <a name="see-also"></a>请参阅  
 [使用平面文件解析引擎](../core/using-the-flat-file-parsing-engine.md)