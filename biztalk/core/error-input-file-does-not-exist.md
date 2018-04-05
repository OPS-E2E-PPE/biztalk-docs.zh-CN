---
title: 错误-输入的文件不存在 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.inputFileDoesNotExist
ms.assetid: 6cd2f076-6c3e-46e3-8be4-dad2d9b95d37
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a14221857ebb567020a52c2ff0939b506d28937
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="error---input-file-does-not-exist"></a>错误-输入的文件不存在
**错误代码**  
  
 btm1037  
  
 **说明**  
  
 为测试映射操作不存在，并输入测试映射的类型未设置为指定的输入的实例消息文件**生成实例**。 时的值**测试映射输入**映射属性未设置为**生成实例**，必须指定现有的实例消息文件进行**测试映射输入实例**将属性映射。  
  
 **用户执行任何操作**  
  
 根据需要，设置下面任一映射属性：  
  
-   **测试映射输入实例。** 右键单击解决方案资源管理器中的相关映射，请单击**属性**，然后在**测试映射**选项卡中**属性页**对话框中的地图中，单击省略号 （**...**) 的值字段中的按钮**测试映射输入实例**属性。 使用**选择输入文件**对话框中，选择现有实例消息符合映射的源架构的文件。 或者，你可以直接的值字段中键入此文件的路径**测试映射输入实例**属性。  
  
-   **测试映射输入。** 若要避免指定输入的实例消息文件，右键单击解决方案资源管理器中的相关映射中，单击**属性**，然后在**测试映射**选项卡**属性页**对于映射，使用下拉列表中的值字段中的对话框**测试映射输入**属性以选择**生成实例**。 在这种情况下，不需要指定的文件**测试映射输入实例**属性。