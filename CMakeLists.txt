cmake_minimum_required(VERSION 3.4.1)

project(webrtc)

set(CMAKE_CXX_STANDARD 17)

set (webrtc_sources

        rtc_base/platform_thread_types.cc
#        test/test_main.cc
#        rtc_base/units/unit_base_unittest.cc
        modules/audio_processing/aec3/echo_canceller3.cc

        modules/audio_processing/aec3/frame_blocker.cc
        modules/audio_processing/aec3/block_framer.cc
        modules/audio_processing/aec3/config_selector.cc
        modules/audio_processing/aec3/multi_channel_content_detector.cc
        modules/audio_processing/aec3/block_delay_buffer.cc
        modules/audio_processing/aec3/block_processor.cc
        modules/audio_processing/aec3/api_call_jitter_metrics.cc
        modules/audio_processing/aec3/render_delay_buffer.cc
        modules/audio_processing/aec3/render_delay_controller.cc
        modules/audio_processing/aec3/echo_remover.cc
        modules/audio_processing/aec3/echo_path_variability.cc
        modules/audio_processing/aec3/block_processor_metrics.cc
        modules/audio_processing/aec3/aec3_common.cc
        modules/audio_processing/aec3/block_buffer.cc
        modules/audio_processing/aec3/spectrum_buffer.cc
        modules/audio_processing/aec3/fft_buffer.cc
#        modules/audio_processing/aec3/fft_data_avx2.cc // INTEL
        modules/audio_processing/aec3/render_buffer.cc
        modules/audio_processing/aec3/downsampled_render_buffer.cc
        modules/audio_processing/aec3/alignment_mixer.cc
        modules/audio_processing/aec3/decimator.cc
        modules/audio_processing/aec3/aec3_fft.cc
        common_audio/third_party/ooura/fft_size_128/ooura_fft.cc
        modules/audio_processing/aec3/echo_path_delay_estimator.cc
        modules/audio_processing/aec3/render_delay_controller_metrics.cc
        modules/audio_processing/aec3/matched_filter.cc
        modules/audio_processing/aec3/subtractor.cc
        modules/audio_processing/aec3/suppression_gain.cc
        modules/audio_processing/aec3/suppression_filter.cc
        modules/audio_processing/aec3/comfort_noise_generator.cc
        modules/audio_processing/aec3/render_signal_analyzer.cc
        modules/audio_processing/aec3/residual_echo_estimator.cc
        modules/audio_processing/aec3/aec_state.cc
        modules/audio_processing/aec3/echo_remover_metrics.cc
        modules/audio_processing/aec3/subtractor_output.cc
        modules/audio_processing/aec3/subtractor_output_analyzer.cc
        modules/audio_processing/aec3/matched_filter_lag_aggregator.cc
        modules/audio_processing/aec3/clockdrift_detector.cc
        modules/audio_processing/aec3/adaptive_fir_filter.cc
        modules/audio_processing/aec3/adaptive_fir_filter_erl.cc
        modules/audio_processing/aec3/coarse_filter_update_gain.cc
        modules/audio_processing/aec3/refined_filter_update_gain.cc
        modules/audio_processing/aec3/moving_average.cc
        modules/audio_processing/aec3/subband_nearend_detector.cc
        modules/audio_processing/aec3/reverb_model.cc
        modules/audio_processing/aec3/transparent_mode.cc
        modules/audio_processing/aec3/erl_estimator.cc
        modules/audio_processing/aec3/filter_analyzer.cc
        modules/audio_processing/aec3/echo_audibility.cc
        modules/audio_processing/aec3/erle_estimator.cc
        modules/audio_processing/aec3/stationarity_estimator.cc
        modules/audio_processing/aec3/reverb_model_estimator.cc
        modules/audio_processing/aec3/reverb_frequency_response.cc
        modules/audio_processing/aec3/reverb_decay_estimator.cc
        modules/audio_processing/aec3/fullband_erle_estimator.cc
        modules/audio_processing/aec3/subband_erle_estimator.cc
        modules/audio_processing/aec3/signal_dependent_erle_estimator.cc
        modules/audio_processing/aec3/dominant_nearend_detector.cc
#        modules/audio_processing/aec3/matched_filter_avx2.cc # INTEL x86
        rtc_base/experiments/field_trial_parser.cc
        modules/audio_processing/logging/apm_data_dumper.cc
        api/audio/echo_canceller3_config.cc
        common_audio/wav_file.cc
        common_audio/wav_header.cc
        rtc_base/string_encode.cc
        rtc_base/time_utils.cc
        rtc_base/system_time.cc
        rtc_base/string_utils.cc
        rtc_base/strings/string_builder.cc
        rtc_base/system/file_wrapper.cc
        rtc_base/logging.cc
        rtc_base/race_checker.cc
#        system_wrappers/source/cpu_features.cc
#        system_wrappers/source/cpu_features_android.cc
        system_wrappers/source/metrics.cc
        system_wrappers/source/field_trial.cc

        modules/audio_processing/ns/speech_probability_estimator.cc
        modules/audio_processing/ns/wiener_filter.cc
        modules/audio_processing/ns/suppression_params.cc
        modules/audio_processing/ns/noise_estimator.cc
        modules/audio_processing/ns/ns_fft.cc
        common_audio/third_party/ooura/fft_size_256/fft4g.cc
        modules/audio_processing/ns/fast_math.cc
        modules/audio_processing/ns/signal_model.cc
        modules/audio_processing/ns/signal_model_estimator.cc
        modules/audio_processing/ns/histograms.cc
        modules/audio_processing/ns/quantile_noise_estimator.cc
        modules/audio_processing/ns/prior_signal_model.cc
        modules/audio_processing/ns/prior_signal_model_estimator.cc
        modules/audio_processing/ns/noise_suppressor.cc

        modules/audio_processing/agc2/gain_applier.cc
        modules/audio_processing/agc2/limiter.cc
        modules/audio_processing/agc2/input_volume_controller.cc
        modules/audio_processing/agc2/noise_level_estimator.cc
        modules/audio_processing/agc2/saturation_protector.cc
        modules/audio_processing/agc2/cpu_features.cc
        modules/audio_processing/agc2/speech_level_estimator.cc
        modules/audio_processing/agc2/adaptive_digital_gain_controller.cc
        modules/audio_processing/agc2/interpolated_gain_curve.cc
        modules/audio_processing/agc2/fixed_digital_level_estimator.cc
        modules/audio_processing/agc2/clipping_predictor.cc
        modules/audio_processing/agc2/input_volume_stats_reporter.cc
        modules/audio_processing/agc2/clipping_predictor_level_buffer.cc
        modules/audio_processing/agc2/saturation_protector_buffer.cc
        modules/audio_processing/agc2/vad_wrapper.cc
        modules/audio_processing/agc2/rnn_vad/features_extraction.cc
        modules/audio_processing/agc2/rnn_vad/pitch_search.cc
        modules/audio_processing/agc2/rnn_vad/spectral_features.cc
        modules/audio_processing/agc2/rnn_vad/spectral_features_internal.cc
        modules/audio_processing/agc2/rnn_vad/rnn_fc.cc
        modules/audio_processing/agc2/rnn_vad/rnn_gru.cc
        modules/audio_processing/agc2/rnn_vad/third_party/rnnoise/src/rnn_vad_weights.cc
        modules/audio_processing/agc2/rnn_vad/lp_residual.cc
        modules/audio_processing/agc2/rnn_vad/pitch_search_internal.cc
        modules/audio_processing/agc2/rnn_vad/auto_correlation.cc
        modules/audio_processing/agc2/rnn_vad/rnn.cc
        modules/audio_processing/agc2/biquad_filter.cc
        modules/audio_processing/utility/third_party/pffft/src/pffft.c
        modules/audio_processing/utility/pffft_wrapper.cc
        modules/audio_processing/gain_controller2.cc
        common_audio/resampler/sinc_resampler.cc
        common_audio/resampler/push_sinc_resampler.cc
        common_audio/resampler/push_resampler.cc
        common_audio/audio_util.cc
        rtc_base/memory/aligned_malloc.cc

        common_audio/signal_processing/splitting_filter.c
        modules/audio_processing/three_band_filter_bank.cc
        modules/audio_processing/splitting_filter.cc
        modules/audio_processing/audio_buffer.cc

#        modules/audio_processing/gain_controller2.cc
#        api/field_trials.cc ###
#        system_wrappers/source/field_trial.cc

        modules/audio_processing/high_pass_filter.cc
        modules/audio_processing/utility/cascaded_biquad_filter.cc
        rtc_base/checks.cc

        modules/third_party/g711/g711.c
    )

set (ABSEIL_DIR ../abseil-cpp)
#set (GTEST_DIR ../googletest/googletest)

add_library(webrtc ${webrtc_sources})

target_compile_definitions(webrtc PRIVATE

        WEBRTC_APM_DEBUG_DUMP=1
        WEBRTC_POSIX=1
        WEBRTC_LINUX=1

        )

## Specify directories which the compiler should look for headers
target_include_directories(webrtc
        PRIVATE .
        PUBLIC .

        ${ABSEIL_DIR}
#        ${GTEST_DIR}
        )

## Compile Flags:
##     Enable -Werror when building debug config
##     Enable -Ofast
#target_compile_options(oboe
#        PRIVATE
#        -std=c++17
#        -Wall
#        -Wextra-semi
#        -Wshadow
#        -Wshadow-field
#        "$<$<CONFIG:RELEASE>:-Ofast>"
#        "$<$<CONFIG:DEBUG>:-O3>"
#        "$<$<CONFIG:DEBUG>:-Werror>")

## Enable logging of D,V for debug builds
#target_compile_definitions(oboe PUBLIC $<$<CONFIG:DEBUG>:OBOE_ENABLE_LOGGING=1>)

#target_link_libraries(oboe PRIVATE log OpenSLES)

# When installing webrtc put the libraries in the lib/<ABI> folder e.g. lib/arm64-v8a
install(TARGETS webrtc
        LIBRARY DESTINATION lib/${ANDROID_ABI}
        ARCHIVE DESTINATION lib/${ANDROID_ABI})

# Also install the headers
install(DIRECTORY include/webrtc DESTINATION webrtc)
