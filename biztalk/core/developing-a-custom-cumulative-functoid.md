---
title: 开发自定义的累积 Functoid |Microsoft 文档
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
ms.openlocfilehash: 9f69ae870269948358f117b07f37d481faced160
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22242325"
---
# <a name="developing-a-custom-cumulative-functoid"></a>开发自定义的累积 Functoid
使用自定义累计 functoid 可以对在一个实例消息中多次出现的值执行累计操作。  
  
 在开发累计 functoid 时，必须实现三个函数。 这三个函数对应于映射执行累计所需的初始化、累计和获取操作。 在讨论这些函数之前，有必要讨论一下线程安全。  
  
## <a name="writing-a-thread-safe-functoid"></a>编写线程安全 Functoid  
 functoid 代码必须为线程安全代码，因为在任务繁忙时，可以同时运行多个映射实例。 应记住以下几点：  
  
-   静态状态必须是线程安全的。  
  
-   实例状态并非始终需要是线程安全的。  
  
-   在设计时应考虑在任务繁忙时的运行情况。 应尽可能避免进行锁定。  
  
-   应尽可能避免进行同步。  
  
 BizTalk Server 提供了一种简单机制，可降低编写线程安全累计 functoid 的复杂度。 所有这三个函数的第一个参数都相同，均为整数索引值。 BizTalk Server 在调用您的初始化函数时会为索引值分配一个唯一的编号。 您可以使用此值作为存放累计值的数组的索引，如以下代码所示：  
  
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
  
 此示例使用 HashTable 而不是 ArrayList。 这是因为初始化函数可能不是按索引值的顺序进行调用。  
  
## <a name="implementing-the-three-cumulative-functions"></a>实现三个累计函数  
 您需要为开发的每个自定义累计 functoid 实现三个函数。 下表概括介绍了这些函数以及为设置这些函数必须在构造函数中调用方法。 所有函数都返回字符串值。  
  
> [!NOTE]
>  由您确定每个函数的最佳名称，但每个函数必须具有所指定的参数数目和类型。  
  
|函数用途|参数|设置引用|设置内联脚本|  
|----------------------|---------------|------------------------|--------------------------|  
|初始化|**int 索引**|**SetExternalFunctionName**|**SetScriptBuffer**与`functionNumber`= 0|  
|累计|**int index、 string val、 string scope**|**SetExternalFunctionName2**|**SetScriptBuffer**与`functionNumber`= 1|  
|获取|**int 索引**|**SetExternalFunctionName3**|**SetScriptBuffer**与`functionNumber`= 2|  
  
### <a name="initialization"></a>初始化  
 通过初始化，您可以准备用于执行累计的机制。 您可以初始化数组，重置一个或多个值，或者根据需要加载其他资源。 不使用字符串返回值。  
  
### <a name="cumulation"></a>累计  
 这是执行与您的 functoid 相应的累计操作的地方。 BizTalk Server 将传入以下三个参数：  
  
-   **索引。** 代表映射实例的整数值。 可以有多个映射实例在同时运行。  
  
-   **Val。** 包含应累计的值的字符串。 除非是在编写字符串累计 functoid，否则该参数为数字值。  
  
-   **作用域。** 包含有数值的字符串，指示应对哪个元素或属性值进行累计。 实际值通过实现来确定。  
  
 由您决定要累计哪些值以及要忽略哪些值。 例如，您可以忽略不小于 0 的值，并在值不是数字时引发异常。 **BaseFunctoid**提供两个函数-**IsDate**和**IsNumeric**-有助于验证。  
  
> [!NOTE]
>  如果你使用**IsDate**或**IsNumeric**在内联脚本中，请务必设置**RequiredGlobalHelperFunctions**以便函数都提供给你的脚本。  
  
 不使用字符串返回值。  
  
### <a name="get"></a>获取  
 BizTalk Server 完成了映射中的 functoid 设置所确定的所有值的循环迭代之后，将请求累计值。 获取函数具有一个参数，即 `Index`，该参数是代表映射实例的整数值。 您的函数应使用索引值来查找累计值并将其作为字符串返回。  
  
## <a name="example"></a>示例  
 下面的示例阐释了如何创建执行累计乘法的自定义 functoid。 该 functoid 依赖于一个包含三个字符串资源和一个 16x16 像素位图资源的资源文件。  
  
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
  
## <a name="see-also"></a>另请参阅  
 [使用 BaseFunctoid](../core/using-basefunctoid.md)   
 [开发自定义的内联 Functoid](../core/developing-a-custom-inline-functoid.md)   
 [自定义 Functoid （BizTalk Server 示例）](../core/custom-functoid-biztalk-server-sample.md)