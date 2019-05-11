---
title: 将 SAP 查询参数转换为 EXECQUERY 命令 mySAP 适配器在 BizTalk 中 |Microsoft Docs
description: SAP 将查询转换为 EXECQUERY，示例的指南
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
ms.openlocfilehash: 8dd9db83cbc3a8b8a3c6a0d56282580f0c07814f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372543"
---
# <a name="translate-sap-query-parameters-into-execquery-command"></a>将 SAP 查询参数转换为 EXECQUERY 命令
介绍如何将查询的参数转换为 EXECQUERY 命令文本。 本主题使用的自定义 SAP 查询 ZQUERY_TST_NEW 示例。  
  
## <a name="open-the-query-in-sap-gui"></a>SAP GUI 中打开查询  
 执行以下步骤以在 SAP 中打开查询。 此处提供的步骤适用于 ZQUERY_TST_NEW 查询，并且特定于 SAP 版本。  
  
1. 运行事务 SQ01。  
  
2. 在中**用户组中的查询**页上，单击**快速查看器**。  
  
3. 在中**快速查看器**页上，在**快速查看**文本框中，键入`ZQUERY_TST_NEW`，然后单击**显示**。  
  
4. 在中**快速查看器**页上，单击**选定内容字段**选项卡可以列出在查询中的所有参数。  
  
    下图显示在查询定义的所有参数。  
  
    ![有关 SAP 查询的参数列表](../../adapters-and-accelerators/adapter-sap/media/sap-query-param-types.gif "sap_query_param_types")  
  
5. 单击 **“执行”**。 将显示以下页面。  
  
    ![为 SAP 查询提供参数值](../../adapters-and-accelerators/adapter-sap/media/sap-query-all-params.gif "sap_query_all_params")  
  
6. 单击黄色箭头来定义每个参数。 您可以定义特定允许/非允许的值也可以定义一系列允许/非允许的值。  必须在每个参数将 SAP GUI 中配置的值指定 EXECQUERY 语法。  
  
   下一节提供有关如何将 SAP GUI 中定义的值以及如何将这些值转换为 EXECQUERY 语法说明。  
  
## <a name="frame-an-execquery-syntax"></a>帧 EXECQUERY 语法  
 让我们看看起来像 EXECQUERY 语法基于查询定义中定义的参数值。 若要理解这一点，我们展示的第一个参数值的配置方式的示例**两位数**，将转换为**ZQUERY_TST_NEW**查询。  
  
 首先，让我们假定中的值**单一 vals** （带有绿色圆点） 的选项卡定义如下面的屏幕截图中所示：  
  
 ![查询可以采用的参数值的列表](../../adapters-and-accelerators/adapter-sap/media/sap-query-param-val.gif "sap_query_param_val")  
  
> [!NOTE]
>  单击黄色箭头后，会显示此对话框**两位数字**参数。  
  
 在这种情况下，EXECQUERY 语法如下所示：  
  
```  
EXECQUERY ZQUERY_TST_NEW @USERGROUP='mygroup', @P1 = '2', @P1 = '3', @P1 = '5'  
```  
  
 为同一查询中，除了中的值**单一 vals**选项卡 （带有绿色圆点），你还可以使用值**单一 vals** （用红点） 的选项卡定义如下所示：  
  
 ![查询不能采用的参数值的列表](../../adapters-and-accelerators/adapter-sap/media/2af88a57-4ff6-4bcc-8961-0f25dbfb8166.gif "2af88a57-4ff6-4bcc-8961-0f25dbfb8166")  
  
 在这种情况下，EXECQUERY 语法如下所示：  
  
```  
EXECQUERY ZQUERY_TST_NEW @USERGROUP='mygroup', @P1 = '2', @P1 = '3', @P1 = '5', NOT @P1 = '6', NOT @P1 = '8'  
```  
  
 现在，如果您将值添加到**范围**选项卡上 （带有绿色圆点），如以下屏幕截图所示：  
  
 ![查询可以采用的参数值的范围](../../adapters-and-accelerators/adapter-sap/media/74907c7d-5a7a-4a2d-a614-6a835eca1764.gif "74907c7d-5a7a-4a2d-a614-6a835eca1764")  
  
 EXECQUERY 语法如下所示：  
  
```  
EXECQUERY ZQUERY_TST_NEW @USERGROUP='mygroup', @P1 = '2', @P1 = '3', @P1 = '5', NOT @P1 = '6', NOT @P1 = '8', @P1 BETWEEN '2' and '5'  
```  
  
 同样，如果您将值添加到**范围**选项卡 （具有一个红点），如以下屏幕截图所示：  
  
 ![查询不能采用的参数值的范围](../../adapters-and-accelerators/adapter-sap/media/ccc6a7bb-bc47-4325-8b58-094201f791bf.gif "ccc6a7bb-bc47-4325-8b58-094201f791bf")  
  
 EXECQUERY 语法如下所示：  
  
```  
EXECQUERY ZQUERY_TST_NEW @USERGROUP='mygroup', @P1 = '2', @P1 = '3', @P1 = '5', NOT @P1 = '6', NOT @P1 = '8', @P1 BETWEEN '2' and '5', NOT @P1 BETWEEN '6' AND '8'  
```  
  
 为简单起见和理解，本主题只讨论的第一个参数**两位数字**。 可以使用类似的方法来确定如何为其他参数定义的值转换为 EXECQUERY 语法。  
  
