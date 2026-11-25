cmake_minimum_required(VERSION 3.22)
project(BackverbPro VERSION 1.0.0)

include(FetchContent)
FetchContent_Declare(
    JUCE
    GIT_REPOSITORY https://github.com/juce-framework/JUCE.git
    GIT_TAG 8.0.4
    GIT_SHALLOW TRUE)
FetchContent_MakeAvailable(JUCE)

juce_add_plugin(Backverb
    COMPANY_NAME "Elite Rec"
    PLUGIN_MANUFACTURER_CODE EliR
    PLUGIN_CODE Bvpr
    FORMATS VST3
    PRODUCT_NAME "Backverb Pro"
    IS_SYNTH FALSE
    NEEDS_MIDI_INPUT FALSE
    NEEDS_MIDI_OUTPUT FALSE
    VST3_CATEGORIES Fx Reverb
    COPY_PLUGIN_AFTER_BUILD FALSE)

target_sources(Backverb PRIVATE
    Source/PluginProcessor.cpp
    Source/PluginProcessor.h
    Source/BackverbDSP.h)

target_compile_definitions(Backverb PUBLIC
    JUCE_WEB_BROWSER=0
    JUCE_USE_CURL=0
    JUCE_VST3_CAN_REPLACE_VST2=0)

target_link_libraries(Backverb
    PRIVATE juce::juce_audio_utils
    PUBLIC juce::juce_recommended_config_flags juce::juce_recommended_warning_flags)
