---
title: 开发自定义累计 Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8ea2c5fa-ed50-4b76-aee9-0d4adf9e6d8c
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 05152065b93fabe103125718334a61da878fd309
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389472"
---
# <a name="developing-a-custom-cumulative-functoid"></a>开发自定义的累计 Functoid
自定义累计 functoid 用于执行累计操作在实例消息中多次出现的值。  
  
 在开发累计 functoid 时，必须实现三个函数。 三个函数对应于初始化、 累计和获取地图需要对其执行累计操作。 在讨论这些函数之前务必讨论一下线程安全。  
  
## <a name="writing-a-thread-safe-functoid"></a>编写线程安全 Functoid  
 Functoid 代码必须是映射的线程安全，因为在任务繁忙多个实例可以同时运行。 一些要记住的要点包括：  
  
- 静态状态必须是线程安全的。  
  
- 实例状态不始终需要是线程安全。  
  
- 设计时应考虑高高负荷环境下运行。 避免进行锁定，只要有可能。  
  
- 如果可能，避免同步需求。  
  
  BizTalk Server 提供了一个简单的机制来降低编写线程安全累计 functoid 的复杂性。 所有三个函数都具有相同的第一个参数为整数索引值。 调用初始化函数时，BizTalk Server 分配到的索引值的唯一编号。 可以使用此值作为索引到一个数组，其中存放累计值，如下面的代码中所示：  
  
```  
private HashTable cumulativeArray = new HashTable();  
…  
// Initialization function  
public string InitCumulativeMultiply(int index)  
{  
    cumulativeArray[index] = 1.0;  
    return string.Empty;  
}  
```  
  
 此示例使用哈希表，而不是 ArrayList。 这是因为初始化函数可能不会调用的顺序索引值。  
  
## <a name="implementing-the-three-cumulative-functions"></a>实现三个累计函数  
 您需要实现的每个开发的自定义累计 functoid 的三个函数。 下表总结了函数和必须在构造函数中设置这些调用的方法。 所有函数返回字符串值。  
  
> [!NOTE]
>  您确定最佳名称对于每个函数，但每个函数必须具有的数量和类型指定的参数。  
  
|函数用途|参数|若要设置的引用|若要设置内联脚本|  
|----------------------|---------------|------------------------|--------------------------|  
|初始化|**int index**|**SetExternalFunctionName**|**SetScriptBuffer**与`functionNumber`= 0|  
|累计|**int index、 string val、 string scope**|**SetExternalFunctionName2**|**SetScriptBuffer**与`functionNumber`= 1|  
|获取|**int index**|**SetExternalFunctionName3**|**SetScriptBuffer**与`functionNumber`= 2|  
  
### <a name="initialization"></a>初始化  
 初始化可准备将用于执行累计的机制。 可以初始化数组、 重置一个或多个值，或根据需要加载其他资源。 字符串返回不使用值。  
  
### <a name="cumulation"></a>累计  
 这是在其中执行相应的 functoid 累计操作。 BizTalk Server 将传入以下三个参数：  
  
- **索引。** 代表映射实例的整数值。 可能有多个映射实例在同时运行。  
  
- **Val。** 包含应累计的值的字符串。 除非你正在编写字符串累计 functoid，它数字值。  
  
- **作用域。** 包含一个数字，指示应累计的元素或属性值的字符串。 实际值由实现决定。  
  
  您决定要累计哪些值以及要忽略哪些值。 例如，可能会忽略不小于 0 的值，但值不是数字时引发异常。 **BaseFunctoid**提供了两个函数 —**IsDate**并**IsNumeric**— 以协助您进行验证。  
  
> [!NOTE]
>  如果您使用**IsDate**或**IsNumeric**中的内联脚本，请务必设置**RequiredGlobalHelperFunctions**以便函数都提供给您的脚本。  
  
 字符串返回不使用值。  
  
### <a name="get"></a>获取  
 BizTalk Server 完成循环访问所有由映射中 functoid 设置的值，它请求的累计的值。 获取函数具有一个自变量， `Index`，这是代表映射实例的整数值。 你的函数应使用的索引值来查找并返回字符串形式的累计的值。  
  
## <a name="example"></a>示例  
 下面的示例说明了如何创建执行累计乘法的自定义 functoid。 它依赖于包含三个字符串资源和 16 x 16 像素位图资源的资源文件。  
  
```  
using System;  
using Microsoft.BizTalk.BaseFunctoids;  
using System.Reflection;  
using System.Text;  
using System.Collections;  
using System.Globalization;  
  
namespace Microsoft.Samples.BizTalk.CustomFunctoid  
{  
    public class CumulativeMultiplyFunctoid : BaseFunctoid  
    {  
        private ArrayList myCumulativeArray = new ArrayList();  
  
        public CumulativeMultiplyFunctoid() : base()  
        {  
            //ID for this functoid  
            ID = 6001;  
  
            // Resource assembly must be ProjectName.ResourceName if building with VS.Net  
            SetupResourceAssembly("Microsoft.Samples.BizTalk.CustomFunctoid.CustomFunctoidResources", Assembly.GetExecutingAssembly());  
  
            // Pass the resource ID names for functoid name, tooltip  
            // description and the 16x16 bitmap for the Map palette  
            SetName("IDS_CUMULATIVEMULTIPLYFUNCTOID_NAME");  
            SetTooltip("IDS_CUMULATIVEMULTIPLYFUNCTOID_TOOLTIP");  
            SetDescription("IDS_CUMULATIVEMULTIPLYFUNCTOID_DESCRIPTION");  
            SetBitmap("IDB_CUMULATIVEMULTIPLYFUNCTOID_BITMAP");  
  
            // Put this string handling function under the Cumulative  
            // Functoid tab in the Visual Studio toolbox for functoids  
            Category = FunctoidCategory.Cumulative;  
  
            // 2 required parameters, no optional parameters  
            SetMinParams(1);  
            SetMaxParams(2);  
  
            // Functoid accepts three inputs  
            AddInputConnectionType(ConnectionType.AllExceptRecord);  
            AddInputConnectionType((~ConnectionType.FunctoidCount) & (~ConnectionType.FunctoidIndex) & (~ConnectionType.FunctoidIteration) & (~ConnectionType.FunctoidCumulative) & (~ConnectionType.FunctoidLooping) & (~ConnectionType.Record));  
            AddInputConnectionType(ConnectionType.AllExceptRecord);  
  
            // Set the output connection type  
            OutputConnectionType = ConnectionType.AllExceptRecord;  
  
            // Set the Initialize, Cumulative and Get functions  
            SetExternalFunctionName(GetType().Assembly.FullName, "Microsoft.Samples.BizTalk.CustomFunctoid.CumulativeMultiplyFunctoid", "InitCumulativeMultiply");  
            SetExternalFunctionName2("AddToCumulativeMultiply");  
            SetExternalFunctionName3("GetCumulativeMultiply");  
        }  
  
        // Initialization function  
        public string InitCumulativeMultiply(int index)  
        {  
            if (index >= 0)  
            {  
                if (index >= myCumulativeArray.Count)  
                {  
                    myCumulativeArray.Add(1.0);  
                }  
                else  
                {  
                    myCumulativeArray[index] = 1.0;  
                }  
            }  
  
            return "";  
        }  
  
        // Cumulative function  
        public string AddToCumulativeMultiply(int index, string val, string reserved)  
        {  
            if (index < 0 || index >= myCumulativeArray.Count)  
            {  
                return "";  
            }  
  
            if (IsNumeric(val))  
            {  
                double dval = Convert.ToDouble(val, CultureInfo.InvariantCulture);  
                myCumulativeArray[index] = (double)(myCumulativeArray[index]) * dval;  
            }  
            return myCumulativeArray[index].ToString();  
        }  
  
        // Get Function  
        public string GetCumulativeMultiply(int index)  
        {  
            if (index < 0 || index >= myCumulativeArray.Count)  
            {  
                return "";  
            }  
  
            return myCumulativeArray[index].ToString();  
        }  
    }  
```  
  
## <a name="see-also"></a>请参阅  
 [使用 BaseFunctoid](../core/using-basefunctoid.md)   
 [开发自定义内联 Functoid](../core/developing-a-custom-inline-functoid.md)   
 [自定义 Functoid（BizTalk Server 示例）](../core/custom-functoid-biztalk-server-sample.md)