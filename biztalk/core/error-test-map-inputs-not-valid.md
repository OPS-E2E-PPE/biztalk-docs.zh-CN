---
title: 错误-测试映射输入无效 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.testMapInputsNotValid
ms.assetid: d885d366-92a3-4d2a-8e2b-58e06960864f
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81aca2f6d941f281a2a720250714c76798762e6b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65346574"
---
# <a name="error---test-map-inputs-not-valid"></a>错误-测试映射输入无效
**错误代码**  
  
 btm1036  
  
 **说明**  
  
 已为测试映射操作指定任何输入的实例消息文件和测试映射输入的类型未设置为**生成实例**。 时的值**测试映射输入**映射属性未设置为**生成实例**，必须指定实例消息文件**测试映射输入实例**映射属性。  
  
 **用户执行任何操作**  
  
 根据需要，设置一个或多个以下映射属性：  
  
-   **测试映射输入实例。** 右键单击解决方案资源管理器中的相关映射，单击**属性**，然后在**测试映射**选项卡中**属性页**对话框的映射，请单击省略号 （**...**) 中的值字段按钮**测试映射输入实例**属性。 使用**选择输入文件**对话框中，选择的实例消息与映射的源架构一致的文件。 或者，直接的值字段中键入此文件的路径**测试映射输入实例**属性。  
  
-   **测试映射输入。** 若要避免指定输入的实例消息文件，右键单击解决方案资源管理器中的相关映射，单击**属性**，然后在**测试映射**选项卡中**属性页**的映射中，使用下拉列表中的值字段对话框**测试映射输入**属性选择**生成实例**。 在这种情况下，您需要指定的文件**测试映射输入实例**属性。