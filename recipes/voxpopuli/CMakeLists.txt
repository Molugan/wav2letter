cmake_minimum_required(VERSION 3.10)

project(wav2letter++-recipes-models-voxpopuli)

# C++ 14 is required
set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# ------------------------- Dedicated SSL Train executable --------------------------
add_executable(
  Train_cpc_voxpopuli
  CPCCriterion.cpp
  Train.cpp
)

add_executable(
  Decode_cpc_voxpopuli
  CPCCriterion.cpp
  Decode.cpp
)

target_link_libraries(
  Train_cpc
  flashlight::flashlight-app-asr
)

target_link_libraries(
  Decode_cpc
  flashlight::flashlight-app-asr
)

