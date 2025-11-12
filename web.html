import React, { useState } from 'react';
import { ArrowRight, ArrowLeft, Share2, Download, Sun, Moon, Activity, Zap, Check } from 'lucide-react';

const RhythmDiagnosisTest = () => {
  const [currentStep, setCurrentStep] = useState(0); // 0: intro, 1-7: questions, 8: result
  const [answers, setAnswers] = useState({});
  const [result, setResult] = useState(null);

  const questions = [
    {
      id: 'q0_gender',
      category: '기본 정보',
      question: '당신의 성별은?',
      survey: true,
      options: [
        { text: '남성', value: 'male' },
        { text: '여성', value: 'female' }
      ]
    },
    {
      id: 'q0_age',
      category: '기본 정보',
      question: '당신의 연령은?',
      survey: true,
      options: [
        { text: '25세~34세', value: '25-34' },
        { text: '35세~40세', value: '35-40' },
        { text: '41세~45세', value: '41-45' },
        { text: '46세 이상', value: '46+' },
        { text: '해당사항 없음', value: 'none' }
      ]
    },
    {
      id: 'q1',
      category: '리듬 인식',
      question: '평일과 주말의 기상 시간이 얼마나 차이나나요?',
      options: [
        { text: '거의 일정하다', value: 3, points: { rhythm: 3 } },
        { text: '1시간 이내', value: 2, points: { rhythm: 2 } },
        { text: '2시간 이상', value: 0, points: { rhythm: 0 } }
      ]
    },
    {
      id: 'q2',
      category: '리듬 인식',
      question: '아침 햇빛을 쬐는 습관이 있나요?',
      options: [
        { text: '매일 15분 이상', value: 3, points: { light: 3 } },
        { text: '가끔', value: 1, points: { light: 1 } },
        { text: '거의 없다', value: 0, points: { light: 0 } }
      ]
    },
    {
      id: 'q3',
      category: '생활 패턴',
      question: '하루 평균 수면시간은?',
      multiple: false,
      options: [
        { text: '불규칙(대충 없다)', value: 0, points: { sleep: 0 } },
        { text: '4시간 미만', value: 0, points: { sleep: 0 } },
        { text: '5~6시간', value: 2, points: { sleep: 2 } },
        { text: '7~8시간', value: 3, points: { sleep: 3 } },
        { text: '8시간 이상', value: 2, points: { sleep: 2 } }
      ]
    },
    {
      id: 'q4',
      category: '생활 패턴',
      question: '기상 후 햇빛 노출 시간은?',
      options: [
        { text: '거의 없음', value: 0, points: { light: 0 } },
        { text: '30분 미만', value: 1, points: { light: 1 } },
        { text: '30분~1시간', value: 2, points: { light: 2 } },
        { text: '2시간 이상', value: 3, points: { light: 3 } }
      ]
    },
    {
      id: 'q5',
      category: '생활 패턴',
      question: '잠들기 전 스마트폰 사용 시간은?',
      options: [
        { text: '거의 보지 않음', value: 3, points: { sleep: 3 } },
        { text: '10분 미만', value: 2, points: { sleep: 2 } },
        { text: '30분 정도', value: 1, points: { sleep: 1 } },
        { text: '1시간 이상', value: 0, points: { sleep: 0 } }
      ]
    },
    {
      id: 'q6',
      category: '생활 패턴',
      question: '하루 평균 활동(걷기/운동) 빈도는?',
      options: [
        { text: '거의 하지 않음', value: 0, points: { activity: 0 } },
        { text: '30분 미만', value: 1, points: { activity: 1 } },
        { text: '1시간 미만', value: 2, points: { activity: 2 } },
        { text: '1시간 이상', value: 3, points: { activity: 3 } }
      ]
    },
    {
      id: 'q7',
      category: '생활 패턴',
      question: '최근 한 달간 가장 힘들었던 점은? (복수 선택 가능)',
      multiple: true,
      options: [
        { text: '😴 수면 패턴 불규칙', value: 'sleep', points: { sleep: -1 } },
        { text: '☀️ 아침 기상 어려움', value: 'light', points: { light: -1 } },
        { text: '🩸 생리주기 불규칙', value: 'cycle', points: { rhythm: -1 } },
        { text: '⚡ 피로감 / 집중력 저하', value: 'activity', points: { activity: -1 } }
      ]
    }
  ];

  const calculateResult = () => {
    const scores = {
      light: 0,
      sleep: 0,
      activity: 0,
      rhythm: 0
    };

    // 서베이 데이터 추출 (결과에 영향 없음)
    const surveyData = {
      gender: answers['q0_gender']?.value || null,
      age: answers['q0_age']?.value || null
    };

    Object.entries(answers).forEach(([key, answer]) => {
      // 서베이 질문은 점수 계산에서 제외
      const question = questions.find(q => q.id === key);
      if (question && question.survey) return;

      if (Array.isArray(answer)) {
        answer.forEach(opt => {
          if (opt.points) {
            Object.entries(opt.points).forEach(([key, value]) => {
              scores[key] += value;
            });
          }
        });
      } else {
        if (answer.points) {
          Object.entries(answer.points).forEach(([key, value]) => {
            scores[key] += value;
          });
        }
      }
    });

    // 진단 로직
    const lightMax = 6;
    const sleepMax = 9;
    const activityMax = 3;
    
    const isLightLow = scores.light < 3;
    const isSleepLow = scores.sleep < 5;
    const isActivityLow = scores.activity <= 1;

    let type = '';
    let title = '';
    let description = '';
    let coaching = '';
    let icon = '';

    if (isLightLow && isSleepLow && isActivityLow) {
      type = 'all-imbalance';
      icon = '🌀';
      title = '리듬 불균형형';
      description = '당신의 생체 리듬은 "리듬 불균형"형이에요. 수면·햇빛·활동의 시간이 엇갈리며, 신체의 \'내적 시계\'가 혼란을 겪고 있어요.';
      coaching = '\'햇빛 → 수면 → 활동\' 순서로 단계별 회복 프로그램을 제안해드려요. FreyaX 리듬 리셋 코칭으로 하루하루 다시 균형을 만들어보세요.';
    } else if (isLightLow && isSleepLow) {
      type = 'light-sleep';
      icon = '🌙';
      title = '혼합 리듬형 (빛+수면)';
      description = '당신의 하루는 햇빛 노출이 부족하고, 수면 리듬이 일정하지 않은 패턴이에요. 특히 아침 햇빛 부족과 취침 전 스마트폰 사용 습관이 체내 생체리듬을 흐트러뜨릴 가능성이 높아요.';
      coaching = '아침에 15분만 햇빛을 쬐어도 내일의 집중력과 기분이 달라져요. FreyaX가 매일 당신의 \'햇빛 루틴\'을 기록하고, 수면 리듬과 주기까지 함께 조율해드릴게요.';
    } else if (isLightLow && isActivityLow) {
      type = 'light-activity';
      icon = '☀️';
      title = '혼합 리듬형 (빛+활동)';
      description = '당신의 하루는 빛과 활동이 모두 부족한 리듬이에요. 이 조합은 낮 동안의 생체 각성을 떨어뜨리고, 저녁의 숙면 리듬에도 영향을 줘요.';
      coaching = '햇빛과 걷기는 최고의 리듬 콤비예요. FreyaX가 햇빛 노출 시간과 걸음 수를 실시간으로 분석하고, \'밝은 하루 루틴\'을 제안해 몸의 리듬을 되살리도록 도울게요.';
    } else if (isSleepLow && isActivityLow) {
      type = 'sleep-activity';
      icon = '💤';
      title = '혼합 리듬형 (수면+활동)';
      description = '당신은 수면의 질과 활동량 모두 불규칙한 리듬이에요. 이 패턴은 피로감, 체온 저하, 집중력 저하로 이어질 수 있어요.';
      coaching = '활동의 균형이 곧 수면의 균형이에요. FreyaX는 수면 시간·활동량을 자동으로 측정하고, 오늘의 컨디션에 맞춘 맞춤형 루틴을 추천해드려요.';
    } else if (isLightLow) {
      type = 'light';
      icon = '🌞';
      title = '빛 부족형';
      description = '당신의 하루는 빛이 부족한 리듬이에요. 햇빛 노출이 부족하면 생체 시계가 혼란스러워지고, 수면 효율이 낮아질 수 있어요.';
      coaching = '햇빛은 하루를 여는 천연 알람이에요. 아침 10시 전 15분만 햇빛을 쬐어보세요. FreyaX CHANDA가 당신의 \'햇빛 루틴\'을 자동으로 기록하고, 빛의 변화가 수면과 주기에 어떤 영향을 주는지 함께 분석해드릴게요.';
    } else if (isSleepLow) {
      type = 'sleep';
      icon = '😴';
      title = '수면 불균형형';
      description = '당신의 수면 리듬이 일정하지 않아요. 불규칙한 취침·기상 패턴은 체내 회복 리듬을 흐트러뜨릴 수 있어요.';
      coaching = '잠이 드는 시간도, 일어나는 시간도 습관이에요. FreyaX CHANDA가 수면 시간과 깊이를 자동으로 분석하고, 당신에게 맞는 \'적정 수면 리듬\'과 코칭 메시지를 매일 제공해드릴게요.';
    } else if (isActivityLow) {
      type = 'activity';
      icon = '🚶';
      title = '활동 저하형';
      description = '당신의 하루는 활동량이 부족한 리듬이에요. 움직임이 줄면 체온과 호르몬 리듬이 저하되어 신체 활력이 떨어질 수 있어요.';
      coaching = '걷기 10분이 내일의 활력을 만듭니다. FreyaX가 걸음 수와 활동 리듬을 자동으로 측정하고, 맞춤형 \'활동 코칭 루틴\'을 통해 일상의 활력을 회복하도록 도와드려요.';
    } else {
      type = 'perfect';
      icon = '✨';
      title = '완벽 리듬형';
      description = '아주 훌륭해요! 매우 이상적인 생체 리듬을 유지하고 계시네요. 몸이 자연의 리듬과 조화를 이루며 안정적으로 회복하고 있다는 뜻이에요.';
      coaching = '지금의 리듬을 꾸준히 이어가세요. FreyaX는 매일 당신의 리듬 데이터를 기록하고, 변화를 실시간으로 분석해 더 완벽한 컨디션 유지를 도와드려요. FreyaX와 함께 꾸준한 리듬을 이어가 보세요.';
    }

    return {
      type,
      icon,
      title,
      description,
      coaching,
      scores
    };
  };

  const handleAnswer = (questionId, option) => {
    const question = questions.find(q => q.id === questionId);
    
    if (question.multiple) {
      const current = answers[questionId] || [];
      const exists = current.find(a => a.value === option.value);
      
      if (exists) {
        setAnswers({
          ...answers,
          [questionId]: current.filter(a => a.value !== option.value)
        });
      } else {
        setAnswers({
          ...answers,
          [questionId]: [...current, option]
        });
      }
    } else {
      setAnswers({
        ...answers,
        [questionId]: option
      });
    }
  };

  const handleNext = () => {
    if (currentStep === questions.length) {
      const diagnosisResult = calculateResult();
      setResult(diagnosisResult);
    }
    setCurrentStep(currentStep + 1);
  };

  const handlePrev = () => {
    setCurrentStep(currentStep - 1);
  };

  const handleRestart = () => {
    setCurrentStep(0);
    setAnswers({});
    setResult(null);
  };

  const canProceed = () => {
    if (currentStep === 0) return true;
    const currentQuestion = questions[currentStep - 1];
    if (!currentQuestion) return false;
    
    const answer = answers[currentQuestion.id];
    if (currentQuestion.multiple) {
      return answer && answer.length > 0;
    }
    return !!answer;
  };

  // Intro Screen
  if (currentStep === 0) {
    return (
      <div className="min-h-screen bg-gradient-to-br from-indigo-50 via-purple-50 to-white flex items-center justify-center p-4">
        <div className="max-w-2xl w-full bg-white rounded-3xl shadow-2xl p-8 md:p-12">
          <div className="text-center space-y-6">
            <div className="w-20 h-20 bg-gradient-to-br from-indigo-600 to-purple-600 rounded-full mx-auto flex items-center justify-center">
              <Activity className="w-10 h-10 text-white" />
            </div>
            <h1 className="text-3xl md:text-4xl font-bold text-gray-900">
              나의 하루 리듬 점검하기
            </h1>
            <p className="text-lg text-gray-600 leading-relaxed">
              5분이면 충분합니다.<br />
              9가지 질문으로 당신의 생체 리듬을 진단하고<br />
              맞춤형 개선 방법을 제안해드릴게요.
            </p>
            <div className="flex flex-wrap justify-center gap-3 pt-4">
              <div className="flex items-center gap-2 px-4 py-2 bg-indigo-50 rounded-full">
                <Sun className="w-5 h-5 text-indigo-600" />
                <span className="text-sm font-medium text-indigo-700">햇빛 노출</span>
              </div>
              <div className="flex items-center gap-2 px-4 py-2 bg-purple-50 rounded-full">
                <Moon className="w-5 h-5 text-purple-600" />
                <span className="text-sm font-medium text-purple-700">수면 패턴</span>
              </div>
              <div className="flex items-center gap-2 px-4 py-2 bg-yellow-50 rounded-full">
                <Activity className="w-5 h-5 text-yellow-600" />
                <span className="text-sm font-medium text-yellow-700">활동량</span>
              </div>
            </div>
            <button
              onClick={handleNext}
              className="mt-8 bg-gradient-to-r from-indigo-600 to-purple-600 text-white px-12 py-4 rounded-full font-semibold hover:shadow-xl transition flex items-center justify-center gap-2 mx-auto group"
            >
              시작하기
              <ArrowRight className="w-5 h-5 group-hover:translate-x-1 transition" />
            </button>
          </div>
        </div>
      </div>
    );
  }

  // Result Screen
  if (currentStep > questions.length && result) {
    // 점수를 퍼센트로 변환
    const lightPercent = Math.round((result.scores.light / 6) * 100);
    const sleepPercent = Math.round((result.scores.sleep / 9) * 100);
    const activityPercent = Math.round((result.scores.activity / 3) * 100);
    const rhythmPercent = Math.round((result.scores.rhythm / 3) * 100);

    return (
      <div className="min-h-screen bg-gradient-to-br from-indigo-50 via-purple-50 to-white p-4 py-12">
        <div className="max-w-3xl mx-auto space-y-6">
          {/* Result Card */}
          <div className="bg-white rounded-3xl shadow-2xl overflow-hidden">
            <div className="bg-gradient-to-r from-indigo-600 to-purple-600 p-12 text-white text-center">
              <div className="text-8xl mb-6 animate-bounce-slow">{result.icon}</div>
              <h2 className="text-2xl font-semibold mb-4 opacity-90">진단 결과</h2>
              <p className="text-4xl md:text-5xl font-bold leading-tight">{result.title}</p>
            </div>
            
            <div className="p-8 space-y-8">
              <div>
                <h3 className="text-xl font-bold text-gray-900 mb-4 flex items-center gap-2">
                  <span className="text-2xl">📊</span>
                  당신의 리듬 분석
                </h3>
                <p className="text-gray-700 leading-relaxed text-lg mb-6">{result.description}</p>
                
                {/* 원형 차트 그래프 */}
                <div className="grid grid-cols-2 md:grid-cols-4 gap-6">
                  {/* 햇빛 */}
                  <div className="flex flex-col items-center">
                    <div className="relative w-28 h-28 mb-3">
                      <svg className="transform -rotate-90 w-28 h-28">
                        <circle
                          cx="56"
                          cy="56"
                          r="50"
                          stroke="#e0e7ff"
                          strokeWidth="12"
                          fill="none"
                        />
                        <circle
                          cx="56"
                          cy="56"
                          r="50"
                          stroke="#4f46e5"
                          strokeWidth="12"
                          fill="none"
                          strokeDasharray={`${2 * Math.PI * 50}`}
                          strokeDashoffset={`${2 * Math.PI * 50 * (1 - lightPercent / 100)}`}
                          strokeLinecap="round"
                          className="transition-all duration-1000"
                        />
                      </svg>
                      <div className="absolute inset-0 flex items-center justify-center">
                        <span className="text-2xl font-bold text-indigo-700">{lightPercent}%</span>
                      </div>
                    </div>
                    <Sun className="w-6 h-6 text-indigo-600 mb-2" />
                    <div className="text-sm font-medium text-gray-700">햇빛</div>
                  </div>

                  {/* 수면 */}
                  <div className="flex flex-col items-center">
                    <div className="relative w-28 h-28 mb-3">
                      <svg className="transform -rotate-90 w-28 h-28">
                        <circle
                          cx="56"
                          cy="56"
                          r="50"
                          stroke="#f3e8ff"
                          strokeWidth="12"
                          fill="none"
                        />
                        <circle
                          cx="56"
                          cy="56"
                          r="50"
                          stroke="#9333ea"
                          strokeWidth="12"
                          fill="none"
                          strokeDasharray={`${2 * Math.PI * 50}`}
                          strokeDashoffset={`${2 * Math.PI * 50 * (1 - sleepPercent / 100)}`}
                          strokeLinecap="round"
                          className="transition-all duration-1000"
                        />
                      </svg>
                      <div className="absolute inset-0 flex items-center justify-center">
                        <span className="text-2xl font-bold text-purple-700">{sleepPercent}%</span>
                      </div>
                    </div>
                    <Moon className="w-6 h-6 text-purple-600 mb-2" />
                    <div className="text-sm font-medium text-gray-700">수면</div>
                  </div>

                  {/* 활동 */}
                  <div className="flex flex-col items-center">
                    <div className="relative w-28 h-28 mb-3">
                      <svg className="transform -rotate-90 w-28 h-28">
                        <circle
                          cx="56"
                          cy="56"
                          r="50"
                          stroke="#fef3c7"
                          strokeWidth="12"
                          fill="none"
                        />
                        <circle
                          cx="56"
                          cy="56"
                          r="50"
                          stroke="#eab308"
                          strokeWidth="12"
                          fill="none"
                          strokeDasharray={`${2 * Math.PI * 50}`}
                          strokeDashoffset={`${2 * Math.PI * 50 * (1 - activityPercent / 100)}`}
                          strokeLinecap="round"
                          className="transition-all duration-1000"
                        />
                      </svg>
                      <div className="absolute inset-0 flex items-center justify-center">
                        <span className="text-2xl font-bold text-yellow-700">{activityPercent}%</span>
                      </div>
                    </div>
                    <Activity className="w-6 h-6 text-yellow-600 mb-2" />
                    <div className="text-sm font-medium text-gray-700">활동</div>
                  </div>

                  {/* 리듬 */}
                  <div className="flex flex-col items-center">
                    <div className="relative w-28 h-28 mb-3">
                      <svg className="transform -rotate-90 w-28 h-28">
                        <circle
                          cx="56"
                          cy="56"
                          r="50"
                          stroke="#dcfce7"
                          strokeWidth="12"
                          fill="none"
                        />
                        <circle
                          cx="56"
                          cy="56"
                          r="50"
                          stroke="#16a34a"
                          strokeWidth="12"
                          fill="none"
                          strokeDasharray={`${2 * Math.PI * 50}`}
                          strokeDashoffset={`${2 * Math.PI * 50 * (1 - rhythmPercent / 100)}`}
                          strokeLinecap="round"
                          className="transition-all duration-1000"
                        />
                      </svg>
                      <div className="absolute inset-0 flex items-center justify-center">
                        <span className="text-2xl font-bold text-green-700">{rhythmPercent}%</span>
                      </div>
                    </div>
                    <Zap className="w-6 h-6 text-green-600 mb-2" />
                    <div className="text-sm font-medium text-gray-700">리듬</div>
                  </div>
                </div>
              </div>

              <div className="relative">
                <div className="absolute inset-0 bg-gradient-to-r from-yellow-100 via-purple-100 to-indigo-100 rounded-3xl blur-xl opacity-50"></div>
                <div className="relative bg-gradient-to-br from-indigo-600 to-purple-600 p-8 rounded-3xl shadow-xl border-4 border-white">
                  <div className="flex items-start gap-4">
                    <div className="flex-shrink-0 w-12 h-12 bg-yellow-400 rounded-full flex items-center justify-center text-2xl shadow-lg">
                      💡
                    </div>
                    <div>
                      <h3 className="text-2xl font-bold text-white mb-4">FreyaX의 맞춤 코칭</h3>
                      <p className="text-white text-lg leading-relaxed opacity-95">{result.coaching}</p>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>

          {/* CTA Section */}
          <div className="bg-white rounded-3xl shadow-xl p-8">
            <h3 className="text-2xl font-bold text-center mb-6 text-gray-900">
              하루의 리듬을 기록하는 습관,<br />
              당신의 내일을 바꿀 첫 걸음입니다.
            </h3>
            <div className="flex flex-col sm:flex-row gap-4 justify-center">
              <button className="bg-gradient-to-r from-indigo-600 to-purple-600 text-white px-8 py-4 rounded-full font-semibold hover:shadow-xl transition flex items-center justify-center gap-2 group">
                FreyaX 앱 다운로드
                <ArrowRight className="w-5 h-5 group-hover:translate-x-1 transition" />
              </button>
              <button className="border-2 border-indigo-600 text-indigo-600 px-8 py-4 rounded-full font-semibold hover:bg-indigo-50 transition">
                CHANDA 둘러보기
              </button>
            </div>
            <div className="flex justify-center gap-4 mt-6">
              <button className="text-sm text-gray-600 hover:text-indigo-600 transition flex items-center gap-1">
                <Share2 className="w-4 h-4" />
                친구에게 공유하기
              </button>
              <button 
                onClick={handleRestart}
                className="text-sm text-gray-600 hover:text-indigo-600 transition"
              >
                다시 테스트하기
              </button>
            </div>
          </div>
        </div>
      </div>
    );
  }

  // Question Screen
  const currentQuestion = questions[currentStep - 1];
  const progress = (currentStep / questions.length) * 100;

  return (
    <div className="min-h-screen bg-gradient-to-br from-indigo-50 via-purple-50 to-white flex items-center justify-center p-4">
      <div className="max-w-2xl w-full">
        {/* Progress Bar */}
        <div className="mb-8">
          <div className="flex justify-between items-center mb-2">
            <span className="text-sm font-medium text-gray-600">
              {currentStep} / {questions.length}
            </span>
            <span className="text-sm font-medium text-indigo-600">
              {Math.round(progress)}%
            </span>
          </div>
          <div className="h-2 bg-gray-200 rounded-full overflow-hidden">
            <div 
              className="h-full bg-gradient-to-r from-indigo-600 to-purple-600 transition-all duration-300"
              style={{ width: `${progress}%` }}
            />
          </div>
        </div>

        {/* Question Card */}
        <div className="bg-white rounded-3xl shadow-2xl p-8 md:p-12">
          <div className="mb-8">
            <div className="inline-block px-4 py-2 bg-indigo-100 text-indigo-700 rounded-full text-sm font-semibold mb-4">
              {currentQuestion.category}
            </div>
            <h2 className="text-2xl md:text-3xl font-bold text-gray-900 leading-tight">
              {currentQuestion.question}
            </h2>
            {currentQuestion.multiple && (
              <p className="text-sm text-gray-500 mt-2">* 복수 선택 가능</p>
            )}
          </div>

          {/* Options */}
          <div className="space-y-3 mb-8">
            {currentQuestion.options.map((option, idx) => {
              const isSelected = currentQuestion.multiple 
                ? (answers[currentQuestion.id] || []).find(a => a.value === option.value)
                : answers[currentQuestion.id]?.value === option.value;

              return (
                <button
                  key={idx}
                  onClick={() => handleAnswer(currentQuestion.id, option)}
                  className={`w-full p-4 rounded-2xl border-2 text-left transition-all ${
                    isSelected
                      ? 'border-indigo-600 bg-indigo-50 shadow-md'
                      : 'border-gray-200 hover:border-indigo-300 hover:bg-indigo-50/50'
                  }`}
                >
                  <div className="flex items-center justify-between">
                    <span className="text-gray-900 font-medium">{option.text}</span>
                    {isSelected && (
                      <div className="w-6 h-6 bg-indigo-600 rounded-full flex items-center justify-center">
                        <Check className="w-4 h-4 text-white" />
                      </div>
                    )}
                  </div>
                </button>
              );
            })}
          </div>

          {/* Navigation Buttons */}
          <div className="flex gap-4">
            {currentStep > 1 && (
              <button
                onClick={handlePrev}
                className="flex-1 border-2 border-gray-300 text-gray-700 px-6 py-4 rounded-full font-semibold hover:bg-gray-50 transition flex items-center justify-center gap-2"
              >
                <ArrowLeft className="w-5 h-5" />
                이전
              </button>
            )}
            <button
              onClick={handleNext}
              disabled={!canProceed()}
              className={`flex-1 px-6 py-4 rounded-full font-semibold transition flex items-center justify-center gap-2 group ${
                canProceed()
                  ? 'bg-gradient-to-r from-indigo-600 to-purple-600 text-white hover:shadow-xl'
                  : 'bg-gray-200 text-gray-400 cursor-not-allowed'
              }`}
            >
              {currentStep === questions.length ? '결과 보기' : '다음'}
              <ArrowRight className="w-5 h-5 group-hover:translate-x-1 transition" />
            </button>
          </div>
        </div>
      </div>
    </div>
  );
};

export default RhythmDiagnosisTest;
