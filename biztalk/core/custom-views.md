---
title: 自定义视图 |Microsoft 文档
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
ms.openlocfilehash: 184f49330374126f4afc0bd4bb376ea31a5ca681
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238165"
---
# <a name="custom-views"></a>自定义视图
自定义视图通常是只读的窗口控件对象 (派生自**System.Windows.Forms.Control**)，以及由要表示的架构中的文件或文件支持的类型为自定义的显示格式的扩展通过 BizTalk 编辑器扩展中。 扩展可以实现多个自定义视图，虽然它不需要具有任何自定义视图。  
  
 自定义视图在 XSD 视图所在的 BizTalk 编辑器窗格中作为附加视图显示，可以通过使用视图底部的选项卡进行访问。 例如，平面文件扩展会添加一个选项卡标记为“平面文件”的新视图。  
  
## <a name="see-also"></a>另请参阅  
 [扩展 BizTalk 编辑器](../core/extending-biztalk-editor.md)