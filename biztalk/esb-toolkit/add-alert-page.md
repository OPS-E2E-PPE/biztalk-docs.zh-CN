---
title: 添加警报页 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0023ee8d-a0d1-4257-95c6-38c95060bd62
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c60c0b495a4d472ea45f9622e61b6a6deb9d95dd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400146"
---
# <a name="add-alert-page"></a>添加警报页
图 1 显示了可以在其中创建新的警报相匹配的警报中指定的条件 （条件） 的错误消息到达门户时，将引发在门户的添加警报页。  
  
 ![添加警报页](../esb-toolkit/media/ch8-addalertpage.gif "Ch8-AddAlertPage")  
  
 **图 1**  
  
 **ESB 管理门户添加警报页**  
  
 在添加警报页，可以执行以下操作：  
  
-   键入新警报的名称**输入警报名称**文本框。  
  
-   指定如何将警报匹配到中的传入异常中字段的值**添加为此警报的条件**此页面部分。 从异常架构选择一个字段 (如**应用程序、 错误类型**或**故障严重性)** 中**条件**下拉列表; 选择比较类型的 （例如，如 =、 **！ =、 > =、 < =、** 或**等**) 中**运算符**下拉列表; 并键入或选择第三个列表中的值。 当您选择的异常字段中，**值**控件更改为文本框或下拉列表，以便输入或选择匹配的值。  
  
-   在选择或输入条件值，单击**添加**链接以添加到列表中的这种情况**条件**部分页上，并重复添加任何需要为此警报的更多条件.  
  
-   单击**保存**按钮以您指定的条件的名称与创建新的警报。