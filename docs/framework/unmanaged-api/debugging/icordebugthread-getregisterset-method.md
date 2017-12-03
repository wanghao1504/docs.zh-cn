---
title: "ICorDebugThread::GetRegisterSet 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread.GetRegisterSet
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread::GetRegisterSet
helpviewer_keywords:
- ICorDebugThread::GetRegisterSet method [.NET Framework debugging]
- GetRegisterSet method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 3b9b6260-98ac-4cfd-88e5-5d7614f94a0c
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9add4dd94669bf41e65793249d05f85700b18cb2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugthreadgetregisterset-method"></a><span data-ttu-id="a7421-102">ICorDebugThread::GetRegisterSet 方法</span><span class="sxs-lookup"><span data-stu-id="a7421-102">ICorDebugThread::GetRegisterSet Method</span></span>
<span data-ttu-id="a7421-103">获取与此 ICorDebugThread 对象的活动部分关联的寄存器集的接口指针。</span><span class="sxs-lookup"><span data-stu-id="a7421-103">Gets an interface pointer to the register set that is associated with the active part of this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7421-104">语法</span><span class="sxs-lookup"><span data-stu-id="a7421-104">Syntax</span></span>  
  
```  
HRESULT GetRegisterSet (  
    [out] ICorDebugRegisterSet **ppRegisters  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a7421-105">参数</span><span class="sxs-lookup"><span data-stu-id="a7421-105">Parameters</span></span>  
 `ppRegisters`  
 <span data-ttu-id="a7421-106">[out]指向的地址的指针[ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)接口对象，表示注册设置此线程的活动部分。</span><span class="sxs-lookup"><span data-stu-id="a7421-106">[out] A pointer to the address of an [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) interface object that represents the register set for the active part of this thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7421-107">要求</span><span class="sxs-lookup"><span data-stu-id="a7421-107">Requirements</span></span>  
 <span data-ttu-id="a7421-108">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a7421-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7421-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a7421-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a7421-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a7421-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a7421-111">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7421-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>