---
title: 自定义视图 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9084cc07-be98-4c57-afea-4fa369a38bad
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 60433668a62c1a7b7483aca3af82ecd8c5d7f8c7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65353324"
---
# <a name="custom-views"></a>自定义视图
自定义视图通常是只读的窗口控件对象 (派生自**System.Windows.Forms.Control**)，并提供的扩展来表示文件或文件支持的类型自定义的显示格式的架构BizTalk 编辑器扩展插件。 扩展可以实现多个自定义视图，但它不需要任何自定义视图。  
  
 自定义视图将显示为在 XSD 视图，通过在视图底部使用选项卡可访问的同一 BizTalk 编辑器窗格中的其他视图。 例如，平面文件扩展与标记为平面文件的选项卡添加一个新的视图。  
  
## <a name="see-also"></a>请参阅  
 [扩展 BizTalk 编辑器](../core/extending-biztalk-editor.md)