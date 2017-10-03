---
title: "高级适配器配置组件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cb31b996-6959-4b5a-9a9f-f48fd91a6180
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8307f54caffec269466dcd9398a9d911fdc83715
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="advanced-configuration-components-for-adapters"></a>适配器的高级的配置组件
BizTalk 适配器框架支持自定义下拉编辑器、自定义模式对话框编辑器和自定义类型转换器。 在将用户名和密码信息作为输入获取的时候，这些自定义设计组件特别有用。  
  
 您可以为配置架构中的特定数据字段（元素或属性）调用自定义编辑器或类型转换器。 在 Microsoft 中所述[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]编辑器必须派生自的帮助， **System.Drawing.Design.UITypeEditor**和从的类型转换器**System.ComponentModel.TypeConverter**。  
  
 编辑器按最小方式将重写**GetEditStyle**方法，以指定编辑器类型 (**模式**对话框中，**下拉列表中**控件，或**无**上述) 和**EditValue**方法可以更改的值与编辑器。  
  
 类型转换器通常替代**ConvertFrom**， **CanConvertFrom**， **ConvertTo**， **CanConvertTo**， **GetStandardValues**， **GetStandardValuesSupported**，和**GetStandardValuesExclusive**的.NET Framework 类库的方法。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [自定义适配器配置设计器](../core/custom-adapter-configuration-designer.md)  
  
-   [适配器配置的的自定义下拉列表编辑器](../core/custom-drop-down-editor-for-adapter-configuration.md)  
  
-   [适配器配置的的自定义模式对话框编辑器](../core/custom-modal-dialog-editor-for-adapter-configuration.md)  
  
-   [适配器配置的的自定义类型转换器](../core/custom-type-converter-for-adapter-configuration.md)