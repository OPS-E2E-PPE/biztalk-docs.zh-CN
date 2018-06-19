---
title: 将转换为 EXECQUERY 命令中 BizTalk mySAP 适配器中 SAP 查询参数 |Microsoft 文档
description: 转换到 EXECQUERY，示例使用的 SAP 查询的指南
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8a545e20-2607-4946-a60d-0a227b86d093
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: efb50db3e499970c0504f81467d382aee31c868f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217725"
---
# <a name="translate-sap-query-parameters-into-execquery-command"></a>将 SAP 查询参数转换为 EXECQUERY 命令
说明如何查询的参数转换成 EXECQUERY 命令文本。 本主题使用自定义的 SAP 查询 ZQUERY_TST_NEW 的示例。  
  
## <a name="open-the-query-in-sap-gui"></a>在 SAP GUI 中打开查询  
 执行以下步骤以在 SAP 中打开查询。 此处提供的步骤适用于 ZQUERY_TST_NEW 查询，特定于 SAP 版本。  
  
1.  运行事务 SQ01。  
  
2.  在**从用户组的查询**页上，单击**快速查看器**。  
  
3.  在**快速查看器**页上，在**快速查看**文本框中，键入`ZQUERY_TST_NEW`，然后单击**显示**。  
  
4.  在**快速查看器**页上，单击**选择字段**选项卡可以列出在查询中的所有参数。  
  
     下图显示在查询定义中的所有参数。  
  
     ![有关 SAP 查询的参数列表](../../adapters-and-accelerators/adapter-sap/media/sap-query-param-types.gif "sap_query_param_types")  
  
5.  单击 **“执行”**。 将显示以下页。  
  
     ![为 SAP 查询提供参数值](../../adapters-and-accelerators/adapter-sap/media/sap-query-all-params.gif "sap_query_all_params")  
  
6.  单击黄色箭头以定义每个参数。 你可以定义特定允许/非允许的值或您可以定义允许/非允许的值的范围。  必须根据配置在 SAP GUI 中的每个参数的值指定 EXECQUERY 语法。  
  
 下一节提供有关如何在 SAP GUI 中定义的值和如何将这些值转换为 EXECQUERY 语法说明。  
  
## <a name="frame-an-execquery-syntax"></a>帧 EXECQUERY 语法  
 我们来看看起来像 EXECQUERY 语法基于查询定义中定义的参数值。 若要理解这一点，我们将显示的值配置的第一个参数的方式示例**两位数**，将转换为**ZQUERY_TST_NEW**查询。  
  
 首先，我们假设中的值**单一 vals** （带有绿色圆点） 的选项卡定义如下面的屏幕截图中所示：  
  
 ![查询可能需要的参数值列表](../../adapters-and-accelerators/adapter-sap/media/sap-query-param-val.gif "sap_query_param_val")  
  
> [!NOTE]
>  单击旁的黄色箭头后，会出现此对话框**两位数**参数。  
  
 在这种情况下，EXECQUERY 语法如下所示：  
  
```  
EXECQUERY ZQUERY_TST_NEW @USERGROUP='mygroup', @P1 = '2', @P1 = '3', @P1 = '5'  
```  
  
 对于相同的查询，除了中的值**单一 vals**选项卡 （带有绿色圆点），你还可以具有值**单一 vals** （包含的一个红点） 的选项卡定义为以下：  
  
 ![查询不能采用的参数值的列表](../../adapters-and-accelerators/adapter-sap/media/2af88a57-4ff6-4bcc-8961-0f25dbfb8166.gif "2af88a57-4ff6-4bcc-8961-0f25dbfb8166")  
  
 在这种情况下，EXECQUERY 语法如下所示：  
  
```  
EXECQUERY ZQUERY_TST_NEW @USERGROUP='mygroup', @P1 = '2', @P1 = '3', @P1 = '5', NOT @P1 = '6', NOT @P1 = '8'  
```  
  
 现在，如果你将值添加到**范围**选项卡上 （带有绿色圆点），如以下屏幕截图所示：  
  
 ![查询可能需要的参数值的范围](../../adapters-and-accelerators/adapter-sap/media/74907c7d-5a7a-4a2d-a614-6a835eca1764.gif "74907c7d-5a7a-4a2d-a614-6a835eca1764")  
  
 EXECQUERY 语法如下所示：  
  
```  
EXECQUERY ZQUERY_TST_NEW @USERGROUP='mygroup', @P1 = '2', @P1 = '3', @P1 = '5', NOT @P1 = '6', NOT @P1 = '8', @P1 BETWEEN '2' and '5'  
```  
  
 同样，如果你将值添加到**范围**选项卡上 （与一个红点），如以下屏幕截图所示：  
  
 ![查询不能采用的参数值的范围](../../adapters-and-accelerators/adapter-sap/media/ccc6a7bb-bc47-4325-8b58-094201f791bf.gif "ccc6a7bb-bc47-4325-8b58-094201f791bf")  
  
 EXECQUERY 语法如下所示：  
  
```  
EXECQUERY ZQUERY_TST_NEW @USERGROUP='mygroup', @P1 = '2', @P1 = '3', @P1 = '5', NOT @P1 = '6', NOT @P1 = '8', @P1 BETWEEN '2' and '5', NOT @P1 BETWEEN '6' AND '8'  
```  
  
 为简单和了解，本主题仅讨论的第一个参数，**两位数**。 可以使用类似的方法来确定如何为其他参数定义的值转换为 EXECQUERY 语法。  
  
