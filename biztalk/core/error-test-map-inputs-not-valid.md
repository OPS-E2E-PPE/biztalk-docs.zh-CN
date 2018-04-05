---
title: 错误-不是有效的测试映射输入 |Microsoft 文档
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
ms.openlocfilehash: 912b70bcd74180a20d54da11dffdab79f54fc5b6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="error---test-map-inputs-not-valid"></a>错误-测试映射输入无效
**错误代码**  
  
 btm1036  
  
 **说明**  
  
 没有输入的实例消息文件已被指定为测试映射操作，且测试映射输入的类型未设置为**生成实例**。 时的值**测试映射输入**映射属性未设置为**生成实例**，必须指定实例消息文件**测试映射输入实例**映射属性。  
  
 **用户执行任何操作**  
  
 根据需要，设置下面任一映射属性：  
  
-   **测试映射输入实例。** 右键单击解决方案资源管理器中的相关映射，请单击**属性**，然后在**测试映射**选项卡中**属性页**对话框中的地图中，单击省略号 （**...**) 的值字段中的按钮**测试映射输入实例**属性。 使用**选择输入文件**对话框中，选择实例消息符合映射的源架构的文件。 或者，你可以直接的值字段中键入此文件的路径**测试映射输入实例**属性。  
  
-   **测试映射输入。** 若要避免指定输入的实例消息文件，右键单击解决方案资源管理器中的相关映射中，单击**属性**，然后在**测试映射**选项卡中**属性页**对于映射，使用下拉列表中的值字段中的对话框**测试映射输入**属性以选择**生成实例**。 在这种情况下，不需要指定的文件**测试映射输入实例**属性。