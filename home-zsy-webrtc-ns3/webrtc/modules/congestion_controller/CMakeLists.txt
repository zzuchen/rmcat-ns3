# c++11 required
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
include_directories(../../../)
include_directories(../../)
set(congestion_controller_FILES
acknowledged_bitrate_estimator.cc
bitrate_estimator.cc
delay_based_bwe.cc
median_slope_estimator.cc
probe_controller.cc
probe_bitrate_estimator.cc
receive_side_congestion_controller.cc
send_side_congestion_controller.cc
transport_feedback_adapter.cc
trendline_estimator.cc
)
add_library(congestion_controller SHARED ${congestion_controller_FILES})
target_link_libraries(congestion_controller remote_bitrate_estimator bitrate_controller rtp_rtcp_format system_wrappers pacing logging rtc_base)
