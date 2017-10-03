---
title: "如何更改单个登录接口的行为 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f4a4946a-e345-4c7e-835d-a3f7f72ebaca
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a4bedc387b879d5ddf21197e3dec4470f2e9b36
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-change-the-behavior-of-a-single-sign-on-interface"></a>如何更改单个登录接口的行为
企业单一登录 (SSO) 对象模型中的许多对象会公开 IPropertyBag 接口，通过它可以修改指定对象的行为。 如果对 SSO 对象调用 QueryInterface，则可以检索 IPropertyBag 接口并用它来更改当前对象的行为。  
  
### <a name="to-change-the-behavior-for-a-specified-sso-interface"></a>更改指定 SSO 接口的行为  
  
1.  在指定接口上使用 QueryInterface 以检索 IPropertyBag 实例。  
  
2.  使用 IPropertyBag.Write 设置接口的属性、类型和值。  
  
     下表介绍了 IPropertyBag propName 和 ptrVar 参数的有效值。  
  
|propName|类型|ptrValue|可用于|  
|--------------|----------|--------------|---------------|  
|CurrentSSOServer|VT_BSTR|信息要发送到的服务器的名称|全部|  
|事务|VT_UNKNOWN<br /><br /> VT_EMPTY|DTC ITransaction 指针，或为 NULL 以清除作用域。|ISSOConfigStore::SetConfigInfo<br />ISSOConfigStore::GetConfigInfo <br />ISSOConfigStore::DeleteConfigInfo<br /><br /> ISSOAdmin::CreateApplication<br />ISSOAdmin::DeleteApplication <br />ISSOAdmin::UpdateApplication<br />ISSOAdmin::CreateFieldInfo<br /><br /> ISSOMapper::GetFieldInfo|  
|AppFilterFlags|VT_I4<br /><br /> VT_UI4|用于控制要筛选的应用程序的标志。|ISSOMapper::GetApplications<br /><br /> ISSOMapper2::GetApplications2|  
|AppFilterFlagsMask|VT_I4<br /><br /> VT_UI4|用于控制要筛选的应用程序的标志掩码。|ISSOMapper::GetApplications<br /><br /> ISSOMapper2::GetApplications2|  
|AsyncCall|VT_BOOL|如果为 True，则使用异步 RPC；如果为 False，则使用同步 RPC。|ISSOConfigOM::GetServerStatus<br /><br /> ISSOAdmin::GetGlobalInfo|  
  
-   **CurrentSSOServer**： 用于确定要 SSO 将信息发送到的服务器，如下所示为的标准行为：  
  
    1.  在注册表中搜索当前用户。 可以使用命令行工具或 GUI 为当前用户设置服务器名称。  
  
    2.  在注册表中搜索所有用户。 可以使用命令行工具或 GUI 为所有用户设置服务器名称。  
  
    3.  如果未在注册表中找到任何 SSO 服务器名称，则使用当前计算机。  
  
     将 CurrentSSOServer 设置为指定服务器会覆盖指定接口的先前处理。 设置 CurrentSSOServer 后，该接口上的所有后续方法调用将发送至指定服务器。  
  
-   **事务**： 指定的 DTC 事务范围内执行的操作 SSO 到对象模型。 您必须在 `ptrValue` 中传递一个 DTC ITransaction 指针，或者传递“null”以清除当前事务作用域。  
  
-   **AppFilterFlags/AppFilterMask**： 控制将哪些类型的应用程序从 ISSOMapper.GetApplications 和 ISSOMapper2.GetApplications 返回。 如果应用程序标志与由筛选器标志和筛选器标志掩码指定的标志相匹配，则会返回这些应用程序标志。 执行应用程序筛选的方法之一是将 AppFilterFlagsMask 设置为 SSO_FLAG_APP_FILTER_BY_TYPE，然后将 AppFilterFlags 设置为以下项中的一项或多项：  
  
     SSO_APP_TYPE_INDIVIDUAL  
  
     SSO_APP_TYPE_GROUP  
  
     SSO_APP_TYPE_CONFIG_STORE  
  
     SSO_APP_TYPE_HOST_GROUP  
  
     SSO_APP_TYPE_PS_ADAPTER  
  
     SSO_APP_TYPE_PS_GROUP_ADAPTER  
  
-   **AsyncCall**： 如果为 true，则 SSO 将执行使用异步的远程过程调用 (RPC) 的方法。 该方法在执行过程中会返回 E_PENDING。 任何其他返回值均表明该方法已完成。 AsyncCall 还允许您进行轮询该方法以确定它是否完成。