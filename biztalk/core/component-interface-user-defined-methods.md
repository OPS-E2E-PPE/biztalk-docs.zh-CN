---
title: 组件接口用户定义的方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- component interfaces, user-defined methods
- user-defined methods, component interface
- custom component interfaces, limitations
- collection limitations
- custom methods, samples
- samples, custom methods
- component interfaces, limitations for custom CI
ms.assetid: e4b15889-35ff-44aa-819d-eade9690bdd6
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1574a73b45f5048910d5df8fee43d75502c2938b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356717"
---
# <a name="component-interface-user-defined-methods"></a>组件接口用户定义的方法
用于 PeopleSoft Enterprise 的 Microsoft BizTalk 适配器在组件接口中支持用户定义的方法。 签名是窗体：  
  
```  
myRet=myCI.myMethod(parameter1, parameter2, ...)  
```  
  
 其中：  
  
- `parameter1``parameter2`是输入的参数。  
  
- `myRet` 是返回值。  
  
  参数只能是该方法的输入的参数。 可以从方法返回一个值，作为返回参数。  
  
> [!NOTE]
>  包含用户定义的方法的组件接口应该只有 PeopleSoft`Get`函数启用。 如果组件接口具有密钥，然后自定义方法将不起作用。  
  
## <a name="custom-ci-limitation"></a>自定义 CI 限制  
 用于 PeopleSoft Enterprise 的 BizTalk 适配器可以处理自定义 PeopleSoft 方法，前提是组件接口没有键。 如果组件接口具有密钥，自定义方法将不起作用。  
  
### <a name="workaround"></a>解决方法  
 创建一个新的组件接口，它不具有键，编写新的自定义方法，将密钥合并为调用的参数的一部分。 例如，可以在 USER_PROFILE 组件接口; 使用 SetPassword 自定义方法但是，USER_PROFILE 具有密钥。 可以创建新的组件接口没有键，，然后在新的组件接口中创建自定义方法。 此方法将接受两个参数，用户 ID 和密码。 自定义的方法可以调用与 USER_PROFILE `Get` ，然后调用`SetPassword`。 有关详细信息，请参阅 PeopleSoft 文档。  
  
 由于在 PeopleSoft 的限制`Date`， `DateTime`，和`Time`出现在用户定义的方法的类型将映射为客户端代码中的字符串。  
  
## <a name="collection-limitation"></a>集合限制  
 用户定义的方法不能返回一个集合，或多个通常情况下，任何 API 对象。 这意味着，您可以只返回简单类型，例如，字符串和数字。 您可以避开此限制通过发送作为 XML 字符串的集合和客户端编程以解析字符串，以将项目提取到正确的格式。 您可以检查 GET_CI_INFO 自定义组件接口，以查看此解决方法的示例。  
  
## <a name="sample-custom-method"></a>示例自定义方法  
 以下基本自定义方法，SayHello，可用于测试组件接口使用自定义方法的功能。  
  
 以下 PeopleCode 函数是名为 ACB_EMPLOYEE PeopleSoft 组件接口的一个用户定义的方法。 该示例返回一个字符串，其中的返回值是**Hello**跟输入参数的值。  
  
```  
Function SayHello(&sName As string) Returns string  
      &EOL = Char(10);  
      &sResult = "Hello " | &sName | &EOL;  
      Return &sResult;  
End-Function;  
```  
  
> [!NOTE]
>  （使用一个命令） 的同时修改多个表可以创建另一个组件接口，或创建一个组件接口用户定义的方法。  
  
## <a name="see-also"></a>请参阅  
 [附录 a:组件接口方法](../core/appendix-a-component-interface-methods.md)