---
title: 使用 BaseFunctoid |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb26a54d-20bf-4302-a5cb-b38e4091002b
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3f2d1381b1babb26324730c301800d6b0909a411
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288709"
---
# <a name="using-basefunctoid"></a>使用 BaseFunctoid
所有自定义 functoid 都必须从 **BaseFunctoid** 类派生。 您必须首先重写该构造函数，并执行一组调用，将您的自定义 functoid 通知给 BizTalk 映射器。 然后需要编写 functoid 逻辑。  
  
## <a name="overriding-the-constructor"></a>重写该构造函数  
 您必须在类构造函数重写方法中执行多个任务来描述 functoid 的特征。 这些任务对解决方案所需的任何特定于 functoid 的代码进行补充。 下表对主要任务进行了说明：  
  
|任务|使用这些方法或属性|注释|  
|----------|-------------------------------------|--------------|  
|为 functoid 分配唯一 ID|**ID**|使用尚未用过的大于 6000 的值。 小于 6000 的值是保留值，供内部 functoid 使用。|  
|指示 functoid 是否具有副作用|**HasSideEffects**|由映射器使用来优化所生成的 XSLT 代码。 默认情况下，此属性为真。|  
|指向资源程序集|**SetupResourceAssembly**|在项目中包含资源文件。 如果使用生成[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，资源程序集必须**ProjectName.ResourceName**。|  
|使自定义 functoid 出现在 BizTalk 映射器面板中|**SetName**<br /><br /> **SetTooltip**<br /><br /> **SetDescription**<br /><br /> **SetBitmap**|使用指向字符串的资源 ID 表示名称、工具提示和说明；使用 16x16 像素的位图。|  
|将 functoid 分配到一个或多个类别中|**类别**|使用一个或多个 [Microsoft.BizTalk.BaseFunctoids.FunctoidCategory](http://msdn.microsoft.com/library/microsoft.biztalk.basefunctoids.functoidcategory.aspx) 值对 functoid 进行分类。|  
|指定接受的参数数量|**SetMinParams**<br /><br /> **SetMaxParams**<br /><br /> **HasVariableInputs**|使用 **SetMinParams** 方法设置必需参数的数量，使用 **SetMaxParams** 方法设置可选参数的数量。 请按照以下准则来设置这些值：<br /><br /> -如果你没有任何可选参数，设置最小值 = 最大值。<br />-如果你拥有某些可选参数，设置最大值 = （多个可选参数的参数的最小数目）。<br />-如果你想要允许不受限制的可选参数，不要设置最大值。<br />-如果你具有可变数量的输入，是否未设置最小值或最大值，并设置**HasVariableInputs** = `true`。|  
|声明可与 functoid 连接的类型|**AddInputConnectionType**|为 functoid 支持的每个 **Microsoft.BizTalk.BaseFunctoids.ConnectionType** 调用一次 [AddInputConnectionType](http://msdn.microsoft.com/library/microsoft.biztalk.basefunctoids.connectiontype.aspx) 。|  
|声明 functoid 可连接到的类型|**OutputConnectionType**|使用 [Microsoft.BizTalk.BaseFunctoids.ConnectionType](http://msdn.microsoft.com/library/microsoft.biztalk.basefunctoids.connectiontype.aspx) 中的值通知 BizTalk 映射器哪些类型的对象可接收 functoid 的输出。 使用 **OR** 可以指定多个连接类型。|  
|通知 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 为 functoid 调用哪些方法|**SetExternalFunctionName**<br /><br /> **SetExternalFunctionName2**<br /><br /> **SetExternalFunctionName3**|对于累计 functoid，请使用 **SetExternalFunctionName** 设置初始化函数，使用 **SetExternalFunctionName2** 设置累计函数，使用 **SetExternalFunctionName3** 指定返回累计值的函数。 对于非累计 functoid，请使用 **SetExternalFunctionName** 设置 functoid 方法。|  
|让 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用内联代码调用 functoid|**AddScriptTypeSupport SetScriptBuffer**|使用 **Microsoft.BizTalk.BaseFunctoids.ScriptType** 调用 [AddScriptTypeSupport](http://msdn.microsoft.com/library/microsoft.biztalk.basefunctoids.scripttype.aspx) 以启用内联代码。 调用 **SetScriptBuffer** 以传入 functoid 的代码。 这些代码将被复制到映射中。|  
|声明内联 functoid 的全局变量|**SetScriptGlobalBuffer**|所做的任何声明对映射中包含的其他内联脚本都是可见的。|  
|指示内联 functoid 需要哪些助手函数|**RequiredGlobalHelperFunctions**|使用 **InlineGlobalHelperFunction** 枚举的值指定需要哪些助手函数。 使用 **OR** 可以指定多个助手函数。|  
|验证传递给 functoid 的参数|**IsDate**<br /><br /> **IsNumeric**|这些函数提供“真/假”答案，而不引发异常。|  
  
## <a name="implementing-functoid-logic"></a>实现 Functoid 逻辑  
 为使 functoid 有用，您必须实现一个或多个方法，方法的数量取决于 functoid 的类别。 如果 functoid 是累计 functoid，则您需要提供三个方法，一个用于初始化，一个执行累计，一个返回累计值。 如果 functoid 不是累计 functoid，则您只需要提供一个返回值的方法。  
  
 而且您还必须确定，内联的 functoid 实现代码应复制到映射中，还是应保留在编译的 .NET 程序集内并通过引用来使用。  
  
 在下列情况下可考虑使用内联 functoid：  
  
-   其他人可以读取并可以修改您的业务逻辑。  
  
-   functoid 只依赖于映射支持的 .NET Framework 命名空间。 有关可用命名空间，请参阅[脚本使用内联 C#、 JScript.NET 和 Visual Basic.NET](../core/scripting-using-inline-csharp-jscript-net-and-visual-basic-net.md)。  
  
-   不需要在 BizTalk 解决方案中部署和维护其他程序集。  
  
-   要编写一系列共享变量的 functoid。  
  
 在下列情况下可考虑使用引用的 functoid：  
  
-   不希望业务逻辑复制到其他人可以看到或能够对其进行修改的映射中。  
  
-   functoid 依赖于映射不支持的 .NET Framework 类。  
  
-   .NET Framework 提供的附加功能要求您的 BizTalk 解决方案部署和维护另一个程序集。  
  
## <a name="see-also"></a>另请参阅  
 [开发自定义引用 Functoid](../core/developing-a-custom-referenced-functoid.md)   
 [开发自定义的内联 Functoid](../core/developing-a-custom-inline-functoid.md)   
 [开发自定义的累积 Functoid](../core/developing-a-custom-cumulative-functoid.md)   
 [Microsoft.BizTalk.BaseFunctoids.BaseFunctoid](http://msdn.microsoft.com/library/Microsoft.BizTalk.BaseFunctoids.BaseFunctoid.aspx)