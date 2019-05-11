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
# <a name="advanced-configuration-components-for-adapters"></a><span data-ttu-id="5a30a-102">适用于适配器的高级的配置组件</span><span class="sxs-lookup"><span data-stu-id="5a30a-102">Advanced Configuration Components for Adapters</span></span>
<span data-ttu-id="5a30a-103">BizTalk 适配器框架支持自定义下拉编辑器、 自定义模式对话框编辑器和自定义类型转换器。</span><span class="sxs-lookup"><span data-stu-id="5a30a-103">The BizTalk Adapter Framework supports a custom drop-down editor, a custom modal dialog editor, and a custom type converter.</span></span> <span data-ttu-id="5a30a-104">创建作为输入的用户名和密码信息时，这些自定义设计组件时特别有用。</span><span class="sxs-lookup"><span data-stu-id="5a30a-104">These custom design components are especially useful when taking user name and password information as input.</span></span>  
  
 <span data-ttu-id="5a30a-105">您可以调用的自定义编辑器或配置架构中的特定数据字段 （元素或属性） 的类型转换器。</span><span class="sxs-lookup"><span data-stu-id="5a30a-105">You can invoke a custom editor or type converter for a specific data field (element or attribute) in the configuration schema.</span></span> <span data-ttu-id="5a30a-106">在 Microsoft 中所述[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]帮助，编辑器必须派生自**System.Drawing.Design.UITypeEditor**并从该类型转换器**System.ComponentModel.TypeConverter**。</span><span class="sxs-lookup"><span data-stu-id="5a30a-106">As described in Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Help, the editor must be derived from **System.Drawing.Design.UITypeEditor** and the type converter from **System.ComponentModel.TypeConverter**.</span></span>  
  
 <span data-ttu-id="5a30a-107">编辑器最小日志将重写**GetEditStyle**方法，以指定编辑器的种类 (**模式**对话框中，**下拉列表中**控件，或**无**的更高版本) 和**EditValue**方法，以便更改与编辑器的值。</span><span class="sxs-lookup"><span data-stu-id="5a30a-107">An editor minimally overrides the **GetEditStyle** method to specify the kind of editor (**Modal** dialog, **DropDown** control, or **None** of the above) and the **EditValue** method to change the value with the editor.</span></span>  
  
 <span data-ttu-id="5a30a-108">类型转换器通常重写**ConvertFrom**， **CanConvertFrom**， **ConvertTo**， **CanConvertTo**， **GetStandardValues**， **GetStandardValuesSupported**，和**GetStandardValuesExclusive**的.NET Framework 类库的方法。</span><span class="sxs-lookup"><span data-stu-id="5a30a-108">A type converter typically overrides the **ConvertFrom**, **CanConvertFrom**, **ConvertTo**, **CanConvertTo**, **GetStandardValues**, **GetStandardValuesSupported**, and **GetStandardValuesExclusive**methods of the .NET Framework Class Library.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5a30a-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="5a30a-109">In This Section</span></span>  
  
-   [<span data-ttu-id="5a30a-110">自定义适配器配置设计器</span><span class="sxs-lookup"><span data-stu-id="5a30a-110">Custom Adapter Configuration Designer</span></span>](../core/custom-adapter-configuration-designer.md)  
  
-   [<span data-ttu-id="5a30a-111">适配器配置的自定义下拉列表编辑器</span><span class="sxs-lookup"><span data-stu-id="5a30a-111">Custom Drop-Down Editor for Adapter Configuration</span></span>](../core/custom-drop-down-editor-for-adapter-configuration.md)  
  
-   [<span data-ttu-id="5a30a-112">适配器配置的自定义模式对话框编辑器</span><span class="sxs-lookup"><span data-stu-id="5a30a-112">Custom Modal Dialog Editor for Adapter Configuration</span></span>](../core/custom-modal-dialog-editor-for-adapter-configuration.md)  
  
-   [<span data-ttu-id="5a30a-113">适配器配置的自定义类型转换器</span><span class="sxs-lookup"><span data-stu-id="5a30a-113">Custom Type Converter for Adapter Configuration</span></span>](../core/custom-type-converter-for-adapter-configuration.md)