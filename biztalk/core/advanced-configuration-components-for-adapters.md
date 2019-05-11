---
title: 适配器的高级配置组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cb31b996-6959-4b5a-9a9f-f48fd91a6180
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 33509a64a80aa27d241a3b2634e89026cecfe0c1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360669"
---
# <a name="advanced-configuration-components-for-adapters"></a>适用于适配器的高级的配置组件
BizTalk 适配器框架支持自定义下拉编辑器、 自定义模式对话框编辑器和自定义类型转换器。 创建作为输入的用户名和密码信息时，这些自定义设计组件时特别有用。  
  
 您可以调用的自定义编辑器或配置架构中的特定数据字段 （元素或属性） 的类型转换器。 在 Microsoft 中所述[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]帮助，编辑器必须派生自**System.Drawing.Design.UITypeEditor**并从该类型转换器**System.ComponentModel.TypeConverter**。  
  
 编辑器最小日志将重写**GetEditStyle**方法，以指定编辑器的种类 (**模式**对话框中，**下拉列表中**控件，或**无**的更高版本) 和**EditValue**方法，以便更改与编辑器的值。  
  
 类型转换器通常重写**ConvertFrom**， **CanConvertFrom**， **ConvertTo**， **CanConvertTo**， **GetStandardValues**， **GetStandardValuesSupported**，和**GetStandardValuesExclusive**的.NET Framework 类库的方法。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [自定义适配器配置设计器](../core/custom-adapter-configuration-designer.md)  
  
-   [适配器配置的自定义下拉列表编辑器](../core/custom-drop-down-editor-for-adapter-configuration.md)  
  
-   [适配器配置的自定义模式对话框编辑器](../core/custom-modal-dialog-editor-for-adapter-configuration.md)  
  
-   [适配器配置的自定义类型转换器](../core/custom-type-converter-for-adapter-configuration.md)