---
title: 高级适配器配置组件 |Microsoft 文档
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
ms.openlocfilehash: 8307f54caffec269466dcd9398a9d911fdc83715
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230005"
---
# <a name="advanced-configuration-components-for-adapters"></a><span data-ttu-id="cfda0-102">适配器的高级的配置组件</span><span class="sxs-lookup"><span data-stu-id="cfda0-102">Advanced Configuration Components for Adapters</span></span>
<span data-ttu-id="cfda0-103">BizTalk 适配器框架支持自定义下拉编辑器、自定义模式对话框编辑器和自定义类型转换器。</span><span class="sxs-lookup"><span data-stu-id="cfda0-103">The BizTalk Adapter Framework supports a custom drop-down editor, a custom modal dialog editor, and a custom type converter.</span></span> <span data-ttu-id="cfda0-104">在将用户名和密码信息作为输入获取的时候，这些自定义设计组件特别有用。</span><span class="sxs-lookup"><span data-stu-id="cfda0-104">These custom design components are especially useful when taking user name and password information as input.</span></span>  
  
 <span data-ttu-id="cfda0-105">您可以为配置架构中的特定数据字段（元素或属性）调用自定义编辑器或类型转换器。</span><span class="sxs-lookup"><span data-stu-id="cfda0-105">You can invoke a custom editor or type converter for a specific data field (element or attribute) in the configuration schema.</span></span> <span data-ttu-id="cfda0-106">在 Microsoft 中所述[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]编辑器必须派生自的帮助， **System.Drawing.Design.UITypeEditor**和从的类型转换器**System.ComponentModel.TypeConverter**。</span><span class="sxs-lookup"><span data-stu-id="cfda0-106">As described in Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Help, the editor must be derived from **System.Drawing.Design.UITypeEditor** and the type converter from **System.ComponentModel.TypeConverter**.</span></span>  
  
 <span data-ttu-id="cfda0-107">编辑器按最小方式将重写**GetEditStyle**方法，以指定编辑器类型 (**模式**对话框中，**下拉列表中**控件，或**无**上述) 和**EditValue**方法可以更改的值与编辑器。</span><span class="sxs-lookup"><span data-stu-id="cfda0-107">An editor minimally overrides the **GetEditStyle** method to specify the kind of editor (**Modal** dialog, **DropDown** control, or **None** of the above) and the **EditValue** method to change the value with the editor.</span></span>  
  
 <span data-ttu-id="cfda0-108">类型转换器通常替代**ConvertFrom**， **CanConvertFrom**， **ConvertTo**， **CanConvertTo**， **GetStandardValues**， **GetStandardValuesSupported**，和**GetStandardValuesExclusive**的.NET Framework 类库的方法。</span><span class="sxs-lookup"><span data-stu-id="cfda0-108">A type converter typically overrides the **ConvertFrom**, **CanConvertFrom**, **ConvertTo**, **CanConvertTo**, **GetStandardValues**, **GetStandardValuesSupported**, and **GetStandardValuesExclusive**methods of the .NET Framework Class Library.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cfda0-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="cfda0-109">In This Section</span></span>  
  
-   [<span data-ttu-id="cfda0-110">自定义适配器配置设计器</span><span class="sxs-lookup"><span data-stu-id="cfda0-110">Custom Adapter Configuration Designer</span></span>](../core/custom-adapter-configuration-designer.md)  
  
-   [<span data-ttu-id="cfda0-111">适配器配置的的自定义下拉列表编辑器</span><span class="sxs-lookup"><span data-stu-id="cfda0-111">Custom Drop-Down Editor for Adapter Configuration</span></span>](../core/custom-drop-down-editor-for-adapter-configuration.md)  
  
-   [<span data-ttu-id="cfda0-112">适配器配置的的自定义模式对话框编辑器</span><span class="sxs-lookup"><span data-stu-id="cfda0-112">Custom Modal Dialog Editor for Adapter Configuration</span></span>](../core/custom-modal-dialog-editor-for-adapter-configuration.md)  
  
-   [<span data-ttu-id="cfda0-113">适配器配置的的自定义类型转换器</span><span class="sxs-lookup"><span data-stu-id="cfda0-113">Custom Type Converter for Adapter Configuration</span></span>](../core/custom-type-converter-for-adapter-configuration.md)