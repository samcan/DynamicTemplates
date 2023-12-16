cmake_minimum_required(VERSION 3.27.0)

project(DynamicTemplates VERSION 2.05 LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)
set(CMAKE_AUTOUIC ON)

find_package(Qt5 REQUIRED COMPONENTS Gui Widgets Svg PrintSupport)

add_executable(diyp
    main.cpp
    MyWindow--createCalendarTab.cpp
    MyWindow--createChartsTab.cpp
    MyWindow--createChecklistsTab.cpp
    MyWindow--createLinesTab.cpp
    MyWindow--createNotesTab.cpp
    MyWindow--createPageSizeTab.cpp
    MyWindow--createTemplateTab.cpp
    MyWindow.cpp
    RenderArea.cpp
    RenderArea/RenderArea--draw.cpp
    RenderArea/RenderArea--drawAppointmentRow.cpp
    RenderArea/RenderArea--drawBar.cpp
    RenderArea/RenderArea--drawGradientBox.cpp
    RenderArea/RenderArea--drawLittleMonth.cpp
    RenderArea/RenderArea--drawOneShortDay.cpp
    RenderArea/RenderArea--drawRow.cpp
    RenderArea/RenderArea--drawShadowedRect.cpp
    RenderArea/RenderArea--drawSubHeader.cpp
    RenderArea/RenderArea--fitRectToString.cpp
    RenderArea/RenderArea--fitStringInRect.cpp
    RenderArea/RenderArea--sets.cpp
    RenderArea/notes/drawSinglePageNotes.cpp
    RenderArea/calendars/onePagePerDay/onePagePerDayDrawPage.cpp
    RenderArea/calendars/onePagePerMonth/onePagePerMonthDrawPage.cpp
    RenderArea/calendars/onePagePerWeek/onePagePerWeekDrawPage.cpp
    RenderArea/calendars/onePagePerYear/onePagePerTwoYearsDrawPage.cpp
    RenderArea/calendars/onePagePerYear/onePagePerYearDrawPage.cpp
    RenderArea/calendars/twoPagePerDay/twoPagePerDayDrawDay.cpp
    RenderArea/calendars/twoPagePerDay/twoPagePerDayDrawOtherPage.cpp
    RenderArea/calendars/twoPagePerMonth/twoPagePerMonthDrawOneDay.cpp
    RenderArea/calendars/twoPagePerMonth/twoPagePerMonthDrawPage.cpp
    RenderArea/calendars/twoPagePerWeek/twoPagePerWeekDrawOneDay.cpp
    RenderArea/calendars/twoPagePerWeek/twoPagePerWeekDrawPage.cpp
    RenderArea/calendars/twoPagePerWeek/twoPagePerWeekMoleskineStyleDrawPage.cpp
    RenderArea/calendars/twoPagePerYear/twoPagePerYearDrawOneDay.cpp
    RenderArea/calendars/twoPagePerYear/twoPagePerYearDrawPage.cpp
)

target_include_directories(diyp PRIVATE "${CMAKE_CURRENT_SOURCE_DIR}")

target_link_libraries(diyp Qt5::Gui Qt5::Widgets Qt5::Svg Qt5::PrintSupport)